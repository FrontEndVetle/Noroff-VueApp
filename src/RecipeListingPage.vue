<template>
    <div class="[ row ]">
        <div v-for="recipe in recipes" :key="recipe" class="[col-sm-12]">
<RecipeListingComponent
v-bind:name = "recipe.title"
v-bind:link = "recipe.href"
v-bind:ingredients = "recipe.ingredients"
v-bind:img = "recipe.thumbnail"

></RecipeListingComponent>

    </div>
    </div>
</template>

<script>
import RecipeListingComponent from './components/RecipeListingComponent'
export default {
    name: 'RecipeListing',
    components: {
    RecipeListingComponent
    },
    data(){
        return{
            recipes:[]
        }
    },
    beforeMount: function(){
        const app = this;

    const conversionUrl = 'https//cors-anywhere.herokuapp.com';
    const url = 'http://www.recipepuppy.com/api/';

    fetch(conversionUrl + url)
    .then(function(response) {
        return response.json
    })
    .then(function(result){
        app.recipes = result;
        console.log(result);
    })
    }
 }
</script>