<template>
  <div id="about">
     <p>
      about works!
    </p>
    <p>
      This is what I'm all about. 
    </p>
    <ul>
      <li v-for='goal in goals'>
        {{goal}}
      </li>
    </ul>
  </div>
</template>

<script>
import DataService from '../DataService'
export default {
  name: 'about',
  data () {
    return {
      goals: DataService.goals
    }
  }
}
</script>
<!-- styling for the component -->
<style>
  @import 'about.css'
</style>