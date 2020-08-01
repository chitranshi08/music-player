<template>
  <div id="app">
    <Music1/>
  </div>
</template>

<script>
import Music1 from './components/Music1.vue'

export default {
  name: 'App',
  components: {
    Music1
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
body{
  background-image:url("./assets/music.jpg");
  background-size:cover;
}
</style>
