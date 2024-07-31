<template>
    <div class="p-8 pb-0">
        <input
            type="text"
            class="rounded border-2 border-gray-200 w-full"
            placeholder="Search for Meals"
            v-model="keyWord"
            @change="searchMeals"
        />
    </div>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
        <div v-for="meal of meals" :key="meal.idMeal" class="bg-white shadow rounded-xl">
            <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
                <img :src="meal.strMealThumb" alt="strMeal" class="rounded-t-xl w-full h-52 object-cover" />
            </router-link>
            <div class="p-3">
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Tenetur voluptatem dolorum et accusantium,
                    sunt recusandae laborum minus optio nulla.
                </p>
                <h3 class="font-bold">{{ meal.strMeal }}</h3>
                <YoutubeButton :href="meal.strYoutube">Go to youtube</YoutubeButton>
            </div>
        </div>
    </div>
</template>
<script setup>
import { computed, onMounted, ref } from 'vue';
import store from '../store';
import { useRoute } from 'vue-router';
import YoutubeButton from '../components/YoutubeButton.vue';

const route = useRoute();
const keyWord = ref('');

const meals = computed(() => store.state.searchMeals);

const searchMeals = () => {
    store.dispatch('searchMeals', keyWord.value);
};

onMounted(() => {
    keyWord.value = route.params.name;
    if (keyWord.value) {
        searchMeals();
    }
});
</script>
