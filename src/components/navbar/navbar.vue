<template>
  <nav class="bg-white fixed w-full z-20 top-0 start-0 border-b border-slate-200 border-b h-[6rem] shadow-sm">
    <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto">
      <a href="#" class="flex items-center space-x-3 rtl:space-x-reverse">
        <img src="../../assets/logo.png" class="h-[7rem] w-[6rem]" alt="Flowbite Logo" />
      </a>
      <div class="flex md:order-2 space-x-3 md:space-x-0 rtl:space-x-reverse mr-3">
        <div class="dropdown inline-block relative">
          <Basebutton name="Telecharger mon CV" icon="ml-1 font-bold ri-download-cloud-2-line text-white text-md" />
          <ul class="dropdown-content absolute hidden text-gray-700 pt-1 space-y-2">
            <li>
              <a href="/cv.pdf" target="_blank" class="block px-4 py-2 text-sm bg-gray-100 shadow rounded text-black font-bold"> <img src="../../assets/fr.png" alt="French Flag" class="w-4 h-4 mr-2 inline-block" /> Français</a>
            </li>
            <li>
              <a href="/cv_en.pdf" target="_blank" class="block px-4 py-2 text-sm bg-gray-100 shadow rounded text-black font-bold"> <img src="../../assets/en.png" alt="English Flag" class="w-4 h-4 mr-2 inline-block" /> English</a>
            </li>
          </ul>
        </div>
      </div>
      <div class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1" id="navbar-sticky">
        <ul class="flex flex-col p-4 md:p-0 mt-4 font-medium rounded-lg md:space-x-8 md:flex-row md:mt-0 md:border-0">
          <li v-for="item in MENUS" :key="item.id" :class="{ 'border-b-2 border-yellow-200 rounded-sm': itemClicked === item.id }" @click="handleItemClick(item.id)">
            <a :href="'#' + item.id" class="block py-2 px-2 text-white rounded md:text-gray-500 md:p-2" aria-current="page">{{ item.title }}</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { MENUS } from "@/constant";
import { onMounted, ref } from "vue";

import Basebutton from "@/components/base/button.vue";

const itemClicked = ref(null);

const handleItemClick = (itemId) => {
  itemClicked.value = itemId;
  // Scroll to the clicked section
  const element = document.getElementById(itemId);
  if (element) {
    element.scrollIntoView({ behavior: "smooth" });
  }
};

onMounted(() => {
  if (MENUS.length > 0) {
    handleItemClick(MENUS[0].id);
  }
});
</script>

<style>
  .dropdown:hover .dropdown-content {
    display: block;
    align-items: center;
  }

  .dropdown-content {
    left: 50%;
  }
</style>
