<template>
<div class="flex justify-center items-center pt-4 mx-auto">
  
  <div class="flex flex-row justify-center border-r-2 border-gray-300">
    <h1 class="mr-2 ml-2 pt-1 font-semibold">Tech Stack</h1>
  </div>

  <div class="flex flex-row justify-center space-x-1 md:space-x-5 card-container ml-2">
    <div v-for="(item, index) in LANGUAGE" :key="index" class="card relative overflow-hidden">
      <img :src="item.image" :alt="item.name" class="rounded h-9 w-9 cursor-pointer mr-3 transition-transform transform hover:scale-105">
    </div>
  </div>
</div>  
</template>
  
  <script setup>
  import { LANGUAGE } from '@/language';
  </script>
  