<template>
  <section class="p-16">
    <header class="text-center">
      <h3 class="text-4xl font-bold text-primary dark:text-white">Education</h3>
    </header>
    <ul class="mt-10 space-y-8 y-8">
      <li
        class="w-full rounded-xl shadow-lg border bg-gradient-to-t to-[#8b22a0] from-[#1f1e1c99]"
        v-for="(item, index) in Education"
        :key="index"
      >
    <a :href="item.link" target="_blank" class="block hover:opacity-80 transition-opacity">
      <article
            class="flex flex-col lg:flex-row items-center lg:items-start rounded-[12px] bg-primary mt-[3px] mx-[3px] p-6 md:p-8 lg:p-10"
          >
          <figure class="w-full lg:w-1/4 flex justify-center lg:justify-start mb-4 lg:mb-0">
              <img :src="item.icon" alt="School Logo" class="w-16 h-16 md:w-20 md:h-20 lg:w-24 lg:h-24 object-contain text-secondary"/>
          </figure>
      
          <section class="w-full lg:w-3/4 lg:pl-4 text-center lg:text-left">
              <header>
                  <h3 class="text-xl md:text-2xl font-semibold uppercase text-secondary">{{ item.School }}</h3>
              </header>
              <p class="text-sm md:text-base text-white">{{ item.degree }}</p>
              <p class="text-sm md:text-base text-white">{{ item.duration }}</p>
          </section>
      </article>
    </a>
      </li>
    </ul>
  </section>
</template>
<script setup>
import { ref } from "vue";
import litoralIcon from '@/assets/ico_gif/litoral.ico';
import iberoIcon from '@/assets/ico_gif/ibero.ico';
const Education = ref([
  {
    duration: "08/2021 - 06/2023",
    School: "Litoral",
    degree: "Professional Technician in Web Programming",
    icon: litoralIcon,
    link: "https://litoral.edu.co/portal/",
  },
  {
    duration: "06/2025 - studying",
    School: "Ibero",
    degree: "Software Engineer",
    icon: iberoIcon,
    link: "https://www.ibero.edu.co",
  },
]);
</script>
