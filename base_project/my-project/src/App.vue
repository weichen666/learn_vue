<template>
  <div id="app">
    <img src="./assets/logo.png">
    <componment-a msgfromfater='you will win!' 
    v-on:child-tell="fromChild"></componment-a>
    <p>{{childMsg}}</p>
    <router-view></router-view>
  </div>
</template>

<script>

import ComponmentA from "./components/ComponmentA"



export default {
  name: 'app',
  data(){
    return {
      childMsg:""
    }
  },
  components:{ComponmentA},
  methods:{
      fromChild:function(msg){
          this.childMsg = msg;
      }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
