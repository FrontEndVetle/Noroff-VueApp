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
import RecipeListingComponent from './components/RecipeListingComponent'
export default {
    name: 'RecipeListingComponent',
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
    })
    }
 }
</script>