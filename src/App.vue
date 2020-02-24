<template lang="html">
<main>
    <h1 id="heading"><u>Recipe Roulette</u></h1>
    <p id="intro">Tired of those same old recipes? <br>Try out our "Recipe Roulette" - a random recipe generator that will have you cooking up something new and exiting at the click of a button!</p>
  <recipes-list :recipes='recipes'></recipes-list>
  <cusines-list :cusines='cusines'></cusines-list>
</main>
</template>

<script>

import RecipesList from './components/RecipesList.vue';
import RecipeListItem from './components/RecipeListItem.vue';
import CusineListItem from './components/CusineListItem.vue';
import CusinesList from './components/CusinesList.vue';
import { eventBus } from './main.js';

export default {

  name: 'app',
    data(){
     return { recipes: [],
      cusines: []
    };
  },
  mounted(){
    fetch("https://www.themealdb.com/api/json/v1/1/random.php")
    .then(result => result.json())
    .then(recipes => this.recipes = recipes['meals'][0])

    fetch("https://themealdb.com/api/json/v1/1/filter.php?a=italian")
    .then(result => result.json())
    .then(cusines => this.cusines = cusines['meals'][0])

    eventBus.$on('recipe-selected', (recipe) => { this.selectedRecipe = recipe})



  },
  components: {
    "recipes-list" : RecipesList,
    "cusines-list" : CusinesList
      }
    }
</script>

<style lang="css" scoped>

main {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background-color:
}

#heading {
  text-align: center;
}

#intro {
  text-align: center;
  font-size: 24px;
}

</style>
