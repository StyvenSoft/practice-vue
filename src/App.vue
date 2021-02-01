<!-- View section -->
<template>
  <Welcome />
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Hello world friends!"/>
</template>

<!-- Logic section -->
<script>
import HelloWorld from './components/HelloWorld.vue'
import Welcome from './components/welcome.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Welcome
  }
}
</script>

<!-- Styles section -->
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
