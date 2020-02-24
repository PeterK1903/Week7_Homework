<template lang="html">

  <div class="">
    <li v-on:click="handleClick">{{recipe.strMeal}}</li>
    </select>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'recipe-list-item',
  props: ['recipe'],
  methods: {
    handleClick(){
      eventBus.$emit('recipe-selected', this.recipe)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
