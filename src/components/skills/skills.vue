<template>
<div class="justify-center items-center flex">
    <h1 class="text-3xl font-light text-transparent bg-clip-text bg-gradient-to-r to-gray-800 from-gray-300 md:text-5xl lg:text-4xl "><span class="underline underline-offset-3 decoration-8 decoration-yellow-200 ">Compétences</span></h1>

</div>

<div class="justify-center items-center flex pt-8">
    <p class="max-w-3xl font-light text-gray-500 lg:mb-8 md:text-lg lg:text-md pt-4 text-center">Je suis spécialisé dans le développement web front-end et back-end, avec une expertise particulière dans les langages comme HTML, CSS, JavaScript et PHP. J'ai également une expérience dans l'utilisation de frameworks comme React.js et Vue.js..</p>
</div>


    <div class="flex justify-center space-x-11 card-container pt-9">
      <div v-for="(item, index) in LANGUAGE" :key="index" class="card" @mouseenter="stopAnimation" @mouseleave="startAnimation">
        <img :src="item.image" :alt="item.name" class="rounded h-20 w-20 cursor-pointer" @mouseover="showName(index)" @mouseout="hideName(index)">
        <div v-show="showNameIndex === index" class="absolute bottom-0 bg-gray-100 border border-black px-2 py-1 rounded">{{ item.name }}</div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import { LANGUAGE } from '@/language';
  
  const showNameIndex = ref(null);
  
  const stopAnimation = () => {
    const cards = document.querySelectorAll('.card');
    cards.forEach(card => card.style.animationPlayState = 'paused');
  }
  
  const startAnimation = () => {
    const cards = document.querySelectorAll('.card');
    cards.forEach(card => card.style.animationPlayState = 'running');
  }
  
  const showName = (index) => {
    showNameIndex.value = index;
  }
  
  const hideName = () => {
    showNameIndex.value = null;
  }
  </script>
  
  <style>
  @keyframes moveCards {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(100%);
    }
  }
  
  .card-container {
    overflow: hidden;
  }
  
  .card {
    animation: moveCards 3s linear infinite;
    position: relative;
  }
  
  .card img {
    transition: filter 0.3s ease-in-out;
  }
  
  .card:hover img {
    filter: brightness(0.8);
  }
  
  .card:hover div {
    visibility: visible;
  }
  
  .card div {
    visibility: hidden;
  }
  </style>
  