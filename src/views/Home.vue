<template>
    <div class="flex p-8 flex-col">
        <div>
            <input type="text" class="rounded border-2 border-gray-200 w-full" placeholder="Search for Meals" />
        </div>
        <div class="flex justify-center gap-2 mt-2">
            <router-link to="/" v-for="(item, index) in letters" :key="index">
                {{ item }}
            </router-link>
        </div>
    </div>
</template>
<script setup>
import { computed } from 'vue';
import store from '../store';

const meals = computed(() => store.state.meals);

const letters = 'ABCDEFGHIJKLM'.split('');
</script>
