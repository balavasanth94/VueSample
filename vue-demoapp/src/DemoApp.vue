<template>
  <img alt="Vue dragon" src="./assets/dragon.png">
  <DemoHome msg="Welcome to Your Demo Application"/>
</template>0

<script>
import DemoHome from './components/DemoHome.vue'

export default {
  name: 'DemoApp',
  components: {
    DemoHome
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