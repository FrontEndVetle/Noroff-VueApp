<template>
    <div class="[ row ]">
        <div v-for="recipe in recepies" class=" [col-sm-12] ">
<recipeListingComponent v-bind:name = "recipe.title"
v-bind:link = "recipe.href"
v-bind:ingredients = "recipe.ingredients"
v-bind:img = "recipe.thumbnail"

></recipeListingComponent>

        </div>
    </div>
</template>