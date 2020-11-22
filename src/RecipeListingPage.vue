<template>
    <div class="row">
        <div class="col-sm-12">
            <h1>Some Excellent Recipes</h1>
        </div>

        <RecipeListingComponent
            v-for="(recipe, count) in recipes"
            v-bind:key="count"
            v-bind:link="recipe.href"
            v-bind:ingredients="recipe.ingredients"
             v-bind:title="recipe.title"
            v-bind:thumbnail="recipe.thumbnail"
        />
    </div>
</template>
<script>
import RecipeListingComponent from './components/RecipeListingComponent';

export default {
  name: 'RecipeListingPage',
  components: {
    RecipeListingComponent
  },
  data() {
    return {
        recipes: []
    }
  },
  created() {
      fetch("https://cors-anywhere.herokuapp.com/http://www.recipepuppy.com/api")
      .then(response => response.json())
      .then(data => {
          this.recipes = data.results;
          for(let i = 0; i < this.recipes.length; i++) {
              this.recipes[i].ingredients = this.recipes[i].ingredients.split(", ");
          }
      })
  }
}
</script>


