<template>
  <div id="app">
  
    <div class="jumbotron my-3">
    <h1>TP6 Fernando Bernasconi</h1>
      <NavBar />      
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'

export default {
  name: 'App',
  components: {
    NavBar
  }
}
</script>

<style>

</style>
