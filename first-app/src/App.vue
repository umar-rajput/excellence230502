<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <Test/> -->
    <!-- <AssignmentFirst/> -->
    <!-- <ListAddData/> -->
    <!-- <Timer/> -->
    <CCard/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import Test from './components/Test.vue'
// import AssignmentFirst from './components/AssignmentFirst.vue'
// import ListAddData from './components/ListAddData.vue';
// import Timer from './components/Timer.vue';
import CCard from './components/CCard.vue' 

export default {
  name: 'App',
  components: {
    // HelloWorld,
    // Test,
    // AssignmentFirst,
    // ListAddData,
    // Timer,
    CCard
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
