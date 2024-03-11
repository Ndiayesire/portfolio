<script setup>
import BaseButton from '@/components/base/button.vue';
import Modal from '@/components/modal/modal.vue';
</script>
<template>
    <div class="justify-center items-center mx-auto flex pt-8 flex-col pt-[5rem]">
      <div>
        <h1 class="text-xl font-bold text-transparent bg-clip-text bg-yellow-200 md:text-xl lg:text-xl  ml-3 mr-3">Expériences</h1>
      <p class="max-w-3xl font-light text-gray-400 lg:mb-8 md:text-lg lg:lg:text-[17px] ml-3 mr-3">
        La section expérience présente un aperçu détaillé de mes parcours professionnels et personnels. 🧠
      </p>
      </div>      
    </div>  
    <div class="justify-center items-center flex flex-col pt-2 ml-2">
      <div>
        <ol class="relative border-s border-gray-300">
          <li class="mb-10 ms-4">
            <div class="absolute w-3 h-3 bg-yellow-300 rounded-full mt-1.5 -start-1.5 border border-white"></div>
            <time class="mb-1 text-sm font-normal leading-none text-gray-400 dark:text-gray-500">2023 - Présent</time>
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white">Crowdchat Canada</h3>
            <p class="mb-4 text-md font-light text-gray-500 dark:text-gray-400">
              Développeur full stack spécialisé en Vue.js et Node.js, je suis responsable de la conception, du développement et de la maintenance d'applications web complètes.
            </p>
          </li>
  
          <li class="mb-10 ms-4">
            <div class="absolute w-3 h-3 bg-yellow-300 rounded-full mt-1.5 -start-1.5 border border-white"></div>
            <time class="mb-1 text-sm font-normal leading-none text-gray-400 dark:text-gray-500">2022 - 2023</time>
            <h3 class="text-lg font-semibold text-gray-900">CSI Keur Madior</h3>
            <p class="mb-4 text-md font-light text-gray-500">Responsable des technologies de l'information, j'étais chargé de superviser l'ensemble des aspects liés aux systèmes informatiques et aux technologies de mon organisation.</p>
          </li>
        </ol>
      </div>
    <BaseButton class="mt-4" name="Voir plus" icon="ri-eye-line"/>
    </div>
  </template>
  