<template>
    <header class="shadow-sm container-fluid bg-white py-3 border-bottom fixed-top">
        <router-link to="/" class="container-md d-flex justify-content-between align-items-center text-decoration-none">
            <img src="@/assets/images/Logo.png" alt="Logo">
            <navigation-bar></navigation-bar>
        </router-link>
    </header>
</template>

<script setup>
    import NavigationBar from './NavigationBar.vue';
</script>