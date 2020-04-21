<template>
  <div id="app">
   
    <app-nav></app-nav>
    <app-home></app-home>
    
  </div>
</template>

<script>
import Home from './components/Home.vue'
export default {
  components:{
    'app-home':Home
  }
}
</script>

<style>

</style>
