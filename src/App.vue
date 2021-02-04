<!-- View section -->
<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Hello world friends!"/>
  <Welcome />
  <SpeedTyper />
</template>

<!-- Logic section -->
<script>
import HelloWorld from './components/HelloWorld.vue'
import Welcome from './components/welcome.vue'
import SpeedTyper from './components/speedTyper.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Welcome,
    SpeedTyper
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
