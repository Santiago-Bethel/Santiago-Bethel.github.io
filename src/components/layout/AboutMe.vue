<template>
  <section class="p-16">
    <header class="text-center">
      <h3 class="text-4xl font-bold text-slate-900 dark:text-white transition-colors">About Me</h3>
    </header>

    <div class="mt-10 flex justify-center">
      <article class="w-full max-w-3xl">
        
        <p class="text-slate-700 dark:text-gray-200 text-lg leading-relaxed text-center md:text-left transition-colors">
          Soy Santiago, un apasionado del desarrollo de software con un enfoque especial en el 
          <strong>Frontend</strong>. Como Técnico Profesional en Programación Web y actual estudiante de 
          Ingeniería de Software, me encanta transformar ideas complejas en interfaces intuitivas y funcionales.
        </p>
        
        <p class="text-slate-700 dark:text-gray-200 text-lg leading-relaxed text-center md:text-left transition-colors">
          Mi stack principal incluye <strong>Vue 3, JavaScript y Spring Boot</strong>. Me considero una persona 
          detallista, autodidacta y con una gran capacidad para adaptarme a nuevas tecnologías. 
          Mi objetivo es seguir creciendo profesionalmente mientras aporto soluciones innovadoras 
          que mejoren la experiencia del usuario.
        </p>

        <div class="mt-8 flex flex-wrap gap-3 justify-center md:justify-start items-center">
          <span v-for="skill in softSkills" :key="skill.id" 
              class="px-4 py-1.5 rounded-full text-xs md:text-sm flex items-center gap-2 border transition-all h-fit w-fit whitespace-nowrap
               bg-slate-200/50 border-slate-300 text-slate-800 
               dark:bg-secondary/20 dark:border-secondary dark:text-white">
            <span class="text-base">{{ skill.icon }}</span>
            <span>{{ skill.name }}</span>
          </span>
        </div>

      </article>
    </div>
  </section>
</template>
<script setup>
import { ref } from "vue";

const softSkills = ref([
  { id: 1, name: "Autodidacta", icon: "📚" },
  { id: 2, name: "Trabajo en Equipo", icon: "🤝" },
  { id: 3, name: "Resolución de Problemas", icon: "💡" },
  { id: 4, name: "Comunicación Asertiva", icon: "🗣️" }
]);
</script>
  