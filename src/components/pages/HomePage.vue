<template>
    <div class="container-md my-5 py-5">
        <div class="recipe__title text-center">
            <h2>All Recipe</h2>
            <p style="font-size: 15px;">
                Lorem ipsum dolor, sit amet consectetur adipisicing elit. Sit deserunt dignissimos aliquam odio fuga rerum, adipisci aut quaerat sequi quidem blanditiis distinctio iste. Culpa quaerat dolorum non dolor cupiditate rerum?
            </p>
        </div>
        <recipe-list
            :recipes="recipeList"
            v-if="recipeListStatus">
        </recipe-list>
    </div>
</template>

<script setup>
import RecipeList from "../recipe/RecipeList.vue";
import { onMounted, ref } from "vue";
import { useStore } from "vuex";

const store = useStore();
const recipeListStatus = ref(false);
const recipeList = ref();

onMounted(async () => {
    try {
        await store.dispatch("recipe/getRecipeData");
        recipeListStatus.value = true;
        recipeList.value = store.state.recipe.recipes;
    } catch (error) {
        console.log(error);
    }
});
</script>