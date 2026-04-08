<template>
  <section id="projects" class="relative w-11/12 px-16 mx-auto">
    <SectionHeader title="My Projects" />
    <!-- Custom Navigation Buttons -->
    <button
      class="swiper-prev absolute top-2/3 left-4 transform -translate-y-1/2 z-10 text-white dark:bg-secondary bg-primary p-4 rounded-full"
    >
      <Icon icon="line-md:arrow-left" class="font-bold text-3xl" />
    </button>
    <button
      class="swiper-next absolute top-2/3 right-4 transform -translate-y-1/2 z-10 text-white dark:bg-secondary bg-primary p-4 rounded-full"
    >
      <Icon icon="line-md:arrow-right" class="font-bold text-3xl" />
    </button>

    <!-- Swiper Component -->
    <swiper
      :effect="'coverflow'"
      grabCursor
      centeredSlides
      :slidesPerView="'auto'"
      :coverflowEffect="{
        rotate: 50,
        stretch: 0,
        depth: 100,
        modifier: 1,
        slideShadows: true,
      }"
      :navigation="navigationOptions"
      loop
      pagination
      :modules="[EffectCoverflow, Navigation]"
      class="max-w-full mt-32"
    >
      <swiper-slide class="max-w-[300px]" v-for="(project,index) in projects" :key="index"> 
        <ProjectCard 
        :title="project.title"
        :description="project.description"
        :image="'src/assets/images/'+project.image"
        :tags="project.tags"
        :liveLink="project.liveLink"
        :codeLink="project.codeLink"
        />
      </swiper-slide>
      
    </swiper>
  </section>
</template>
<script setup>
import SectionHeader from "@/components/UI/SectionHeader.vue";
import ProjectCard from "@/components/UI/ProjectCard.vue";
import "swiper/css";
import "swiper/css/effect-coverflow";
import "swiper/css/navigation";
import "swiper/css/pagination";
import { Swiper, SwiperSlide } from "swiper/vue";
import { EffectCoverflow, Navigation } from "swiper/modules";
import { ref } from "vue";

//Define navigation options
const navigationOptions = {
  prevEl: ".swiper-prev",
  nextEl: ".swiper-next",
};

const projects=ref([
    {
        title:'Crud Sencillo',
        description:'Un sistema Crud basico de eliminar, guardar y modificar productos hecho en Java',
        image: new URL('../assets/images/Crud-sencillo.png', import.meta.url).href, 
        tags:['Java'],
        codeLink:"https://github.com/Santiago-Bethel/Crud_sencillo"
    },
    {
        title:'Memory Game',
        description:'Un juego de cartas de memoria con efectos de sonido, temporizador y contador de intentos',
        image: new URL('../assets/images/Memory-game.png', import.meta.url).href,
        tags:['HTML','Vue','CSS','Typescript'],
        codeLink:"https://github.com/Santiago-Bethel/Memory-Game"
    },
    {
        title:'Product Page',
        description:'Durante mis varios cambios de Pc perdí varios proyectos, solo me quedaron los más básicos y quiero empezar para mejorar este Portafolio con una página de venta de X producto y expandirlo a futuro con su Dashboard de productos',
        image: new URL('../assets/images/proximamente.png', import.meta.url).href,
        tags:['HTML','Vue','CSS','Typescript'],
        codeLink:"/"
    },
    {
        title:'Crud Sencillo',
        description:'Un sistema Crud basico de eliminar, guardar y modificar productos hecho en Java',
        image: new URL('../assets/images/Crud-sencillo.png', import.meta.url).href,
        tags:['Java'],
        codeLink:"https://github.com/Santiago-Bethel/Crud_sencillo"
    },
    {
        title:'Memory Game',
        description:'Un juego de cartas de memoria con efectos de sonido, temporizador y contador de intentos',
        image: new URL('../assets/images/Memory-game.png', import.meta.url).href,
        tags:['HTML','Vue','CSS','Typescript'],
        codeLink:"https://github.com/Santiago-Bethel/Memory-Game"
    },
    {
        title:'Product Page',
        description:'Durante mis varios cambios de Pc perdí varios proyectos, solo me quedaron los más básicos y quiero empezar para mejorar este Portafolio con una página de venta de X producto y expandirlo a futuro con su Dashboard de productos',
        image: new URL('../assets/images/proximamente.png', import.meta.url).href,
        tags:['HTML','Vue','CSS','Typescript'],
        codeLink:"/"
    },
    

])
</script>
<style>
.swiper-button-prev,
.swiper-button-next{
    cursor: pointer;
}
.swiper-slide{
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
