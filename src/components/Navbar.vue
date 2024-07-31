<template>
    <header class="h-16 bg-white shadow flex justify-between items-center">
        <router-link :to="{ name: 'home' }" class="flex items-center justify-center h-full px-5">Home</router-link>
        <div class="h-full px-5">
            <router-link
                :to="{ name: 'byName' }"
                class="px-2 h-full inline-flex justify-center items-center hover:bg-purple-100 transition-colors duration-300"
            >
                Search Meals
            </router-link>
            <router-link
                :to="{ name: 'byLetter' }"
                class="px-2 h-full inline-flex justify-center items-center hover:bg-purple-100 transition-colors duration-300"
            >
                Meals By Letter
            </router-link>
            <router-link
                :to="{ name: 'byIngredient' }"
                class="px-2 h-full inline-flex justify-center items-center hover:bg-purple-100 transition-colors duration-300"
            >
                Meals By Ingredients
            </router-link>
        </div>
    </header>
</template>
<script setup></script>
