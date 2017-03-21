<template>
	<div class="hello">
		<h1>{{msg}}</h1>
		<h1>{{msgfromfater}}</h1>
		<button @click="onClickMe">Click</button>
	</div>
</template>


<script>
	export default{
		data(){
			return{
				msg: "Hello World",
			}
		},
		props:["msgfromfater"],
		methods:{
			onClickMe: function(){
				this.$emit("child-tell", "加油！")
			}
		}
	}
</script>


<style>
	h1{
		color:#42b983;
	}

</style>