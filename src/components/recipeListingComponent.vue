<template>
    <div class="[ row ]">
    <div class="[col-sm-4]">
        <div class="[ card ]"></div>
        <div class="[ card-information ]">
            Name: {{name}}
            Link: {{link}}
            Ingredients: {{ingredients}}
            image: {{img}}

        </div>
    </div>
    </div>
</template>

<script>
export default {
    name: 'Recepies',
    props: ['name', 'link', 'intredients', 'img'],
}
</script>