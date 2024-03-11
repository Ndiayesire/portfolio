<template>
  <div class="justify-center items-center mx-auto flex pt-8 flex-col pt-[3rem]">
    <div>
      <h1 class="text-xl font-bold text-transparent bg-clip-text bg-yellow-200 md:text-xl lg:text-xl ml-3 mr-3">Projets</h1>
      <p class="max-w-3xl font-light text-gray-400 lg:mb-8 md:text-lg lg:lg:text-[17px] ml-3 mr-3">
        Vous savez comment c'est avec les portfolios des programmeurs : nous n'avons pas toujours le temps de les mettre à jour car nous sommes souvent très occupés à rendre les projets de nos clients exceptionnels.💡
      </p>
    </div>
  </div>

  <div class="flex justify-center pt-3" v-for="(item, index) in PROJECT" :key="index">
    <div class="flex flex-col space-y-5 lg:flex-row lg:space-x-10 lg:space-y-0 pt-3">
      <img :src="item.image" class="w-[27rem] h-[16rem] max-w-full rounded-lg mr-5 shadow" />
      <div class="flex flex-col justify-center items-center">
        <h1 class="font-semibold text-gray-600">{{ item.name }}</h1>
        <p class="font-light max-w-sm text-gray-400 pt-2">{{ item.description }}</p>
        <p class="mt-4 font-semibold text-gray-600 cursor-pointer">{{ item.language }}</p>
        <div class="flex space-x-8 mb-0">
          <p class="mt-8 font-semibold text-gray-600 cursor-pointer">Code <i class="ri-github-fill text-2xl text-black"></i></p>
          <p class="mt-8 font-semibold text-gray-600 cursor-pointer">Live Demo <i class="ri-external-link-line text-2xl text-black"></i></p>
        </div>
      </div>
    </div>
  </div>
  <br />
</template>

<script setup>
  import { PROJECT } from "@/project";
  import BaseButton from "@/components/base/button.vue";
</script>
