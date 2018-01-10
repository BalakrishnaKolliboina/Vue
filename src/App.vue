<template>
  <div id="app">
    <ul>
      <li><router-link v-bind:to="'/'">Home</router-link></li>
      <li><router-link v-bind:to="'/about'">About</router-link> </li>
    </ul>
  
       
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>


<style>
@import 'styles.css'
</style>
