<template>
  <div id="app">
    <h1> W19a: Vue Playlist </h1>
  

  <Events  />
  <VuePlaylist  />
  </div>
</template>

<script>
import Events from './components/Events.vue'
import VuePlaylist from './components/VuePlaylist.vue'


export default {
  name: 'App',
  components: {
   VuePlaylist,
   Events
   
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
