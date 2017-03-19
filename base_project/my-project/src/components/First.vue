<template>
	<div class="first">
		{{msg}}
		<input type="text" @keyup.enter="onEnter" v-model="text">
		<ul>
			<li v-for="item in items" :class="{finish:item.isFinish}" 
				v-on:click="changeStatus(item,  $event)">
				{{item.label}}
			</li>
		</ul>

	</div>
</template>

<script>

	import store from "@/store"

	export default {
	  	name: 'first',
	  	data (){
	    	return {
	      		msg: 'Love Wang YY',
	      		items: store.fetch(),
	      		text:""
	    	}
  		},
  		methods:{
  			"changeStatus": function(item){
  					item.isFinish = !item.isFinish;
  			},
  			"onEnter":function(){
  				this.items.push({label:this.text, isFinish:false});
  				this.text = "";
  			}
  		},
  		watch:{
  			items:{
  				handler: function(val, oldval){
  					store.save(val)
  				},
  				deep:true
  			}
  		}
	}
</script>

<style>
	.finish{
		text-decoration: underline;
	}

</style>