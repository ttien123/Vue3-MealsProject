<template>
    <a
        :href="href"
        target="_blank"
        class="block px-3 py-2 border-red-600 border text-center mt-4 rounded text-red-600 hover:bg-red-600 hover:text-white transition-all duration-300"
    >
        <slot></slot>
    </a>
</template>
<script setup>
const props = defineProps({
    href: String,
    isTest: Boolean,
});
</script>
