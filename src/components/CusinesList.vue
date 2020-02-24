<template lang="html">
<main>

  <p id="wheeltitle"> Want more options but still want to leave it all up to chance? </p>
  <p id="wheeltitle"> Then spin our magic wheel and select your given cusine, to start your culinary adventure! </p>
  <p align="center"><iframe id="wheel" src="https://wheeldecide.com/e.php?c1=Chinese&c2=American&c3=British&c4=French&c5=Italian&c6=Indian&c7=Spanish&c8=Greek&c9=Turkish&col=light&t=The+Wheel+Of+Mystery%21&time=5" width="500" height="500" scrolling="no" frameborder="0"></iframe></p>
  <h3><u>Italian: {{cusines.strMeal}}</u></h3>
  <img :src="cusines.strMealThumb" height="400"/>
</main>

</template>

<script>

import {eventBus} from '../main.js'

export default {

  name: 'cusines-list',
    data(){
      return{
        cusine: null
      }
    },
  props: ['cusines'],
  methods: {
    handleChange(){
      eventBus.$emit('cusine-selected', this.cusine)
    }
  }
}
</script>

<style lang="css" scoped>

#wheeltitle {
  text-align: center;
}

#wheel {
 display:block;
}


</style>
