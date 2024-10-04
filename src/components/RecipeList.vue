<script setup>
import RecipeCard from './RecipeCard.vue';

</script>

<template>
<div class="grid grid-cols-5 gap-10 p-10">
    <RecipeCard v-for="card in 20" :key="card"></RecipeCard>
</div>


</template>