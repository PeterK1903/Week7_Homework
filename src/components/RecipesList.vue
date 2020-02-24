<template lang="html">

<main>

 <h3><u>{{recipes.strMeal}}</u></h3>
 <img id="recipe-photo" :src="recipes.strMealThumb" height="400"/>
 <button id="refresh" onclick="location.reload();">Fancy something else?</button>
<h1 id="iheading"> <u>Instructions:</u></h1>
 <p id="instructions">{{recipes.strInstructions}} </p>
 <hr id="hrleft">
<br>
<h1><u>Cook-along Video:</u></h1>
 <iframe
 width="560"
 height="315"
 :src="recipes.strYoutube.replace('watch?v=', 'embed/')"
 frameborder="0"
 allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
 allowfullscreen></iframe>
 <hr id="hrright">
<h1 id="ingredients"> <u>Ingredients:</u></h1>
<table align="right">
  <tr>
    <th>Food Stuff</th>
    <th>Measurement(s)</th>
  </tr>
  <tr>
    <td>{{recipes.strIngredient1}}</td>
    <td>{{recipes.strMeasure1}}</td>
  </tr>
    <tr>
      <td>{{recipes.strIngredient2}}</td>
      <td>{{recipes.strMeasure2}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient3}}</td>
      <td>{{recipes.strMeasure3}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient4}}</td>
      <td>{{recipes.strMeasure4}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient5}}</td>
      <td>{{recipes.strMeasure5}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient6}}</td>
      <td>{{recipes.strMeasure6}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient7}}</td>
      <td>{{recipes.strMeasure7}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient8}}</td>
      <td>{{recipes.strMeasure8}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient9}}</td>
      <td>{{recipes.strMeasure9}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient10}}</td>
      <td>{{recipes.strMeasure10}}</td>
    </tr>
    <!-- <tr>
      <td>{{recipes.strIngredient11}}</td>
      <td>{{recipes.strMeasure11}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient12}}</td>
      <td>{{recipes.strMeasure12}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient13}}</td>
      <td>{{recipes.strMeasure13}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient14}}</td>
      <td>{{recipes.strMeasure14}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient15}}</td>
      <td>{{recipes.strMeasure15}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient16}}</td>
      <td>{{recipes.strMeasure16}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient17}}</td>
      <td>{{recipes.strMeasure17}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient18}}</td>
      <td>{{recipes.strMeasure18}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient19}}</td>
      <td>{{recipes.strMeasure19}}</td>
    </tr>
    <tr>
      <td>{{recipes.strIngredient20}}</td>
      <td>{{recipes.strMeasure20}}</td>
    </tr> -->
</table>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>
</main>
</template>

<script>

import {eventBus} from '../main.js'

export default {

  name: 'recipes-list',
    data(){
      return{
        recipe: null
      }
    },
  props: ['recipes'],
  methods: {
    handleChange(){
      eventBus.$emit('recipe-selected', this.recipe)

      location.reload();
    }
  }
}
</script>

<style lang="css" scoped>

#refresh {
  display: block;
 margin-left: auto;
 margin-right: auto;
  padding: 12px 23px;
  font-size: 24px;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
  outline: none;
  color: #fff;
  background-color: black;
  border: none;
  border-radius: 15px;
  box-shadow: 0 9px #999;
}

#refresh:hover {background-color: black}

#refresh:active {
  background-color: black;
  box-shadow: 0 5px #666;
  transform: translateY(4px);
}

#hrleft {
  border: 0;
  height: 1.5px;
  background-image: linear-gradient(to left rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0));
}

#hrright {
  border: 0;
  height: 1.5px;
  background-image: linear-gradient(to right rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0));
}

h3 {
  text-align: center;
}

table {
  font-family: arial, sans-serif;
  align-items:R center;
  width: 50%;
}

td, th {
  border: 1px solid #dddddd;
  text-align: right;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}

#recipe-photo {
  display: block;
 margin-left: auto;
 margin-right: auto;
}

#iheading {
  text-align: right;
}

#instructions {
  text-align: right;
}

#ingredients {
  text-align: right;
}

</style>
