<template>
  <div id="app">
    
    <!-- <img alt="Vue logo" src="./assets/stairs.jpg" height="900"> -->
    <portfolio/>
    <technologies/>
  </div>
</template>

<script>
import Portfolio from './components/Portfolio.vue'
import Technologies from './components/Technologies.vue'

export default {
  name: 'app',
  components: {
    Portfolio,
    Technologies
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
