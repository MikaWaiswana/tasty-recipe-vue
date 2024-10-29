<template>
    <div class="col-12 col-sm-8">
        <recipe-description></recipe-description>
        <recipe-directions></recipe-directions>
        <recipe-ingredients></recipe-ingredients>
    </div>
</template>

<script setup>
import { onMounted } from "vue";
import { useRoute } from "vue-router";
import { useStore } from "vuex";
import RecipeDescription from './RecipeDescription.vue';
import RecipeDirections from "./RecipeDirections.vue";
import RecipeIngredients from "./RecipeIngredients.vue";

const store = useStore ()
const route = useRoute ()

onMounted(async () => {
    await store.dispatch (
        "recipe/getRecipeDetail", route.params.id
    )
})
</script>