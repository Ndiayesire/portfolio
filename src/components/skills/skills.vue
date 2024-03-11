<template>
<div class="flex justify-center items-center pt-4 mx-auto">
  
  <div class="flex flex-row justify-center border-r-2 border-gray-400">
    <h1 class="font-semibold mr-3 pt-1">Je suis spécialité en</h1>
  </div>

  <div class="flex flex-row justify-center space-x-1 md:space-x-9 card-container ml-7">
    <div v-for="(item, index) in LANGUAGE" :key="index" class="card relative overflow-hidden">
      <img :src="item.image" :alt="item.name" class="rounded h-9 w-9 cursor-pointer">
    </div>
  </div>
</div>  
</template>
  
  <script setup>
  import { LANGUAGE } from '@/language';
  </script>
  