<script setup>
  import { ref } from "vue";
  import Navbar from "@/components/navbar/navbar.vue";
  import Hero from "@/components/hero/hero.vue";
  import Skills from "@/components/skills/skills.vue";
  import Project from "@/components/project/project.vue";
  import Footer from "@/components/footer/footer.vue";
  import Competence from "@/components/competence/competence.vue";

  const isLoading = ref(true);
  
  setTimeout(() => {
    isLoading.value = false;
  }, 2000);

</script>

<template>
  <div v-if="isLoading" class="flex justify-center items-center h-screen">
    <div class="loader">
        <div class='loader-center'>
    <div class='chars text-5xl'>
      <span class='char brace text-gray-500'>{</span>
      <span class='dots'>
        <span class='char dot _dot-1 text-yellow-300'>.</span>
        <span class='char dot _dot-2 text-yellow-300'>.</span>
        <span class='char dot _dot-3 text-yellow-300'>.</span>
      </span>
      <span class='char brace text-gray-500'>}</span>
    </div>
  </div>
</div>
  </div>
  <div v-else class="">
    <Navbar />
    <Hero :id="0"/>
    <Skills :id="1"/>
    <Competence :id="2"/>
    <Project :id="3"/>
    <footer/>
  </div>
</template>

<style scoped>
section.loader {
  font-family: Consolas, monaco, monospace;
  position:absolute;
  top:0; left:0; right:0; bottom:0;
  background-color:#232427;
  
  color:#FF893A;
}

section.loader .loader-center {
  width:300px;
  height:100px;
  line-height:100px;
  
  margin:0 auto;
  text-align:center;
  font-size:38px;
  letter-spacing:-6px;
  
  position:absolute;
  top:50%; left:50%;
  margin-left:-150px; margin-top:-50px;
  
}

section.loader .loader-center .chars .dots .char {
  font-size:150%;
  display:inline-block;
}

/* animation starts here */
.dots .dot {
  position:relative;
  top:0; left:0; 
}

.dot._dot-1 {
  animation:dot_1 1s ease-in-out infinite;
  animation-fill-mode: backwards;
  animation-direction: alternate;
}

.dot._dot-2 {
  animation:dot_2 1s ease-in-out infinite;
  animation-fill-mode: backwards;
  animation-direction: alternate;
  animation-delay:1s;
}

.dot._dot-3 {
  animation:dot_3 1s ease-in-out infinite;
  animation-fill-mode: backwards;
  animation-direction: alternate;
  animation-delay:0.5s;
}


@keyframes dot_1 {
  0% {
    top:0;
    left:0;
  }
  
  50% {
    top:30px;
    left:20px;
  }
  
  100% {
    top:0px;
    left:40px;
  }
}


@keyframes dot_2 {
  0% {
    top:0;
    left:0;
  }
  
  50% {
    top:-30px;
    left:20px;
  }
  
  100% {
    top:0px;
    left:40px;
  }
}


@keyframes dot_3 {
  0% {
    top:0;
    left:0;
  }
  
  50% {
    top:-30px;
    left:-40px;
  }
  
  100% {
    top:0px;
    left:-80px;
  }
}
</style>
