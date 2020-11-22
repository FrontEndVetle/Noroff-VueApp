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
    props: ['name', 'link', 'ingredients', 'img'],
}
</script>