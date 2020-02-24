<template lang="html">

  <div class="">
    <li v-on:click="handleClick">{{cusine.strMeal}}</li>
    </select>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'cusine-list-item',
  props: ['cusine'],
  methods: {
    handleClick(){
      eventBus.$emit('cusine-selected', this.cusine)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
