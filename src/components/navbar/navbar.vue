<script setup>
import { MENUS } from '@/constant';
import Basebutton from '@/components/base/button.vue';
import { onMounted, ref } from 'vue';

const itemClicked = ref(null);

const handleItemClick = (itemId) => {
  itemClicked.value = itemId;
};

onMounted(() => {
  if (MENUS.length > 0) {
    handleItemClick(MENUS[0].id);
  }
});
</script>

<template>
  <nav class="bg-white w-full z-20 top-0 start-0 border-b border-gray-200 border-b h-[6rem]">
    <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto">
      <a href="#" class="flex items-center space-x-3 rtl:space-x-reverse">
        <img src="../../assets/logo.png" class="h-[7rem] w-[6rem]" alt="Flowbite Logo">
      </a>
      <div class="flex md:order-2 space-x-3 md:space-x-0 rtl:space-x-reverse">
        <Basebutton name="Telecharger CV" icon="ml-1 font-bold ri-download-cloud-2-line text-white text-md"/>
        <button data-collapse-toggle="navbar-sticky" type="button" class="inline-flex items-center w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none " aria-controls="navbar-sticky" aria-expanded="false">
          <i class="ri-menu-line"></i>
        </button>
      </div>
      <div class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1" id="navbar-sticky">
        <ul class="flex flex-col p-4 md:p-0 mt-4 font-medium rounded-lg md:space-x-8 md:flex-row md:mt-0 md:border-0">
          <li v-for="item in MENUS" :key="item.id" :class="{ 'border-b-2 border-yellow-200 rounded-sm': itemClicked === item.id }" @click="handleItemClick(item.id)">
            <a href="#" class="block py-2 px-2 text-white rounded md:text-gray-500 md:p-2" aria-current="page">{{ item.title }}</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>
