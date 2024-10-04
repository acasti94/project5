<script setup>
import { faker } from '@faker-js/faker'

const recipeName = faker.lorem.words(3) 
const cookingTime = faker.datatype.number({ min: 10, max: 120 }) 
const description = faker.lorem.lines(2) 
const ingredients = [
  faker.food.ingredient(),
  faker.food.ingredient(),
  faker.food.ingredient(),
  faker.food.ingredient()
] 

const username = faker.internet.userName({ firstName: recipeName }).toLowerCase() 
</script>

<template>
  <RouterLink :to="{ name: 'CardDetails', params: { id: username }}">
    <div class="border border-gray-400 rounded-xl shadow bg-gray-200 h-full">
      <img :src="faker.image.food(640, 480, true)" class="rounded-t-xl" alt="Recipe Image" />
      <div class="p-4">
        <p class="mb-2 text-2xl font-bold">{{ recipeName }}</p>
        <p class="mb-3 font-normal text-gray-700">Cooking Time: {{ cookingTime }} minutes</p>
        <p class="mb-3 font-normal text-gray-700">Ingredients: {{ ingredients.join(', ') }}</p>
        <p class="mb-3 font-normal text-gray-700">{{ description }}</p>
      </div>
    </div>
  </RouterLink>
</template>