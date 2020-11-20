<template>
  <div id="app">
    <RecipeListingComponent hello="recepies" />
  </div>
</template>

<script>
import RecipeListingComponent from './components/recipeListingComponent.vue'
export default {
  name: 'App',
  components: {

    RecipeListingComponent
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
