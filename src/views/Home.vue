<template>
    <div class="flex p-8 flex-col">
        <div class="flex justify-center gap-2 mt-2">
            <router-link v-for="(letter, index) of letters" :key="index" :to="{ name: 'byLetter', params: { letter } }">
                {{ letter }}
            </router-link>
        </div>
    </div>
</template>
<script setup>
import { computed, onMounted, ref } from 'vue';
import store from '../store';
import axiosClient from '../axiosClient';
const meals = computed(() => store.state.meals);
const letters = 'ABCDEFGHIJKLM'.split('');
const ingredients = ref([]);

onMounted(async () => {
    const response = await axiosClient.get('list.php?i=list');
    ingredients.value = response.data;
});
</script>
