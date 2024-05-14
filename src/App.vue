<template>
  <img alt="Vue logo" class="logo" src="./assets/reshot.svg">
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <BuildOne/>
  <BuildTwo/>
  
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import BuildOne from './components/BuildOne.vue'
import BuildTwo from './components/BuildTwo.vue'
export default {
  name: 'App',
  components: {
    // HelloWorld,
    BuildOne,
    BuildTwo
    
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
.logo{
  height: 40px;
}
</style>
