<template>
    <div class="col-sm-3">
        <div class="card">
            <img class="card-img" v-bind:src="thumbnail" alt="image of food">
            <div class="card-body">
                <h2>{{title}}</h2>
                <ul>
                    <li
                        v-for="(ingredient, count) in ingredients"
                        v-bind:key="count"
                    >{{ingredient}}</li>
                </ul>

                <a v-bind:href="link">Click me</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'RecipeListingComponent',
  props: {
      title: String,
      thumbnail: String,
      link: String,
      ingredients: Array
  }
}
</script>

<style scoped>
h1 {
    font-size : 20px;

}
h2 {
    font-size : 18px;

}

.card{
    border: 2px solid green;

}
a {
    border: 2px solid red;
    margin: 5px;
    padding: 5px;
}
</style>