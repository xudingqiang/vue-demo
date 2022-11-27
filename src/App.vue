<template>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <!-- <TestComputed></TestComputed> -->
  <!-- <PersonCompVue></PersonCompVue> -->
  <FormComp></FormComp>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import TestComputed from './components/TestComputed.vue'
// import PersonCompVue from './components/PersonComp.vue';
import  FormComp from './components/FormComp.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    // TestComputed,
    // PersonCompVue,
    FormComp
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
