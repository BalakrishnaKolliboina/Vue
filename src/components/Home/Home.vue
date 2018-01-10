<template>
  <div id="home">
    <div class="container color-dark">
      <div class="col">
        <p>Add a bucket list item</p>
      </div>
      <div class="col">
        <p>Your bucket list ({{itemCount}})</p>
      </div>
    </div>
    <div class="container color-light">
      <div class="col">
        <p class="sm">Use this form below to add a new bucket list goal. What do you want to accomplish in your life?</p>

        <form>
          <input type="text" class="txt" name="item" placeholder="Life goal.." v-model='goalText'>

          <input type="button" class="btn" v-model='btnText' @click = "addItem()">
        </form>
      </div>
      <div class="col">
       <transition-group name="fadeDown" tag="ul">
        <p class="life-container" v-for='goal in goals' v-bind:key='goal'>          
          {{goal}}        
        </p>
        </transition-group>
      </div>
    </div>
  </div>
</template>

<script>
import DataService from '../DataService'
export default {
  name: 'home',
  data () {
    return {
      itemCount: DataService.goals.length,
      btnText: 'Add an Item',
      goals: DataService.goals,
      goalText: 'My first life goal',
      addItem: function () {
        this.goals.push(this.goalText)
        this.itemCount = this.goals.length
      }
    }
  }
}
</script>

<style>
@import 'Home.css'
</style>
