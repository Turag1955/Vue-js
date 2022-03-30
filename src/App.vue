<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <HomeTest data="i am turag" msg="users"/>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import HomeTest from './components/HomeTest.vue'

export default {
  name: 'App',
  data(){
    return {
      users: [
        {name:'anil'},
        {name:'tanil'},
        {name:'canil'},
        {name:'kanil'},
      ]
    }
  },
  components: {
    // HelloWorld,
    HomeTest
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
