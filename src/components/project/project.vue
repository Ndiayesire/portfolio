<template>
  <div class="justify-center items-center flex pt-[3rem]">
    <h1 class="text-3xl font-light text-transparent bg-clip-text bg-gradient-to-r to-gray-800 from-gray-300 md:text-5xl lg:text-4xl"><span class="underline underline-offset-3 decoration-8 decoration-yellow-200">Mes Projets</span></h1>
  </div>

  <div class="justify-center items-center flex pt-8">
    <p class="max-w-3xl font-light text-gray-500 lg:mb-8 md:text-lg lg:text-md pt-4 text-center">
      Ceci n'est qu'une petite partie des excellents clients avec lesquels j'ai collaboré. Vous savez comment c'est avec les portfolios des programmeurs : nous n'avons pas toujours le temps de les mettre à jour car nous sommes souvent très
      occupés à rendre les projets de nos clients exceptionnels. 😍
    </p>
  </div>

  <div class="justify-center items-center flex pt-5">
    <div class="grid grid-cols-1 gap-5 sm:grid-cols-3 md:grid-cols-3">
      <div v-for="(item, index) in PROJECT" :key="index" class="relative mr-4 ml-4">
        <img class="object-cover object-center w-[37rem] h-[25rem] max-w-full rounded-lg rounded opacity-80 shadow cursor-pointer" :src="`/src/assets/${item.image}`"  alt="gallery-photo" />
        <div class="absolute inset-0 flex items-center justify-center bg-gradient-to-r to-gray-500 from-gray-300 bg-opacity-50 opacity-0 hover:opacity-90 transition transform hover:scale-105 transition-opacity duration-300 cursor-pointer hover:rounded-lg">
          <div class="text-center bg-yellow-200 w-[20rem] h-[2rem] rounded shadow">
            <p class="font-bold text-gray-600 pt-1"><i class="ri-links-line"></i> {{ item.name }}</p>
          </div>
          
        </div>
      </div> 
    </div>
  </div>
  <br />
</template>

<script setup>
import { PROJECT } from '@/project';
</script>
