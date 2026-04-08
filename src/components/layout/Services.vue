<template>
  <section id="services" class="relative text-white mt-32">
    <SectionHeader title="Services I Offer" />
    <div
      class="mt-20 py-8 xl:px-16 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
    >
      <article
        class="px-[12px] mb-[24px]"
        v-for="element in services"
        :key="element.id"
      >
        <div
          class="mt-[30px] relative flex flex-col justify-center text-center rounded-[30px] border border-secondary dark:bg-[#ffffff29] bg-primary"
          data-aos="fade-up"
          :data-aos-delay="element.id * 100"
        >
          <div class="mt-[-30px] flex justify-center relative">
            <div class="mt-[-7px] p-[20px] relative bg-primary rounded-[50%]">
              <span
                class="h-[60px] w-[60px] m-auto border-[1px] border-solid border-secondary absolute top-[8px] left-[8px] rounded-[50%] inline-block z-[5]"
              ></span>
              <img
                :src="element.icon"
                alt="services"
                class="h-[35px] w-[35px] relative z-[1]"
              />
            </div>
          </div>
          <div class="p-[30px]">
            <h3 class="uppercase font-semibold text-secondary text-base">
              {{ element.name }}
            </h3>
            <p
              class="text-[14px] leading-[20px] text-white trackaing-[0.03rem]"
            >
              {{ element.description }}
            </p>
          </div>
        </div>
      </article>
    </div>
  </section>
</template>
<script setup>
import { ref } from "vue";
import SectionHeader from "@/components/UI/SectionHeader.vue";

const services = ref([
  {
    id: 1,
    icon: "/src/assets/ico_gif/codificacion.gif",
    name: "Custom Dashboard Development",
    description:
      "Gracias a mi dominio de Vue 3 y JavaScript, puedo ofrecer la creación de paneles de administración para negocios. Estos permitirán visualizar datos, ventas o inventarios de forma interactiva.",
  },
  {
    id: 2,
    icon: "/src/assets/ico_gif/codificacion.gif",
    name: "High-Conversion Landing Page Creation",
    description:
      "Utilizando HTML5 y CSS3 avanzado, puedo diseñar sitios de una sola página enfocados en vender un producto o servicio específico. Dando valor a la optimización: sitios que cargan rápido, son totalmente responsive (se ven bien en el celular) y tienen animaciones fluidas que atrapan al usuario.",
  },
  {
    id: 3,
    icon: "/src/assets/ico_gif/creador-de-sitios-web.gif",
    name: "UI Refactoring & Interface Modernization",
    description:
      "Muchos negocios tienen sistemas antiguos (hechos en PHP básico o Java viejo) que funcionan pero se ven mal. Puedo ofrecer el servicio de lavado de cara migrando esas interfaces a Vue 3 o mejorando el CSS, haciendo que la experiencia del usuario sea moderna, rápida y atractiva sin tocar la lógica pesada del backend.",
  },
  {
    id: 4,
    icon: "/src/assets/ico_gif/codificacion.gif",
    name: "Design Systems Development",
    description:
      "Para empresas que están creciendo, puedo ofrecer la creación de una librería de componentes en Figma (botones, tipografías, tarjetas, formularios) que luego programaré en Vue 3. Asegurando que toda la plataforma del cliente tenga una identidad visual coherente y sea fácil de mantener a largo plazo.",
  },
  {
    id: 5,
    icon: "/src/assets/ico_gif/creador-de-sitios-web.gif",
    name: "Design-to-Code Implementation (Figma to Code)",
    description:
      "Muchos diseñadores gráficos crean interfaces increíbles en herramientas como Figma pero no saben programarlas. Puedo ofrecer el servicio técnico de traducir esos diseños a código HTML/CSS/JS perfecto, pixel por pixel.",
  },
  {
    id: 6,
    icon: "/src/assets/ico_gif/creador-de-sitios-web.gif",
    name: "UI/UX Design & Prototyping",
    description:
      "Antes de escribir una sola línea en Vue 3, ofrezco diseñar la aplicación en Figma. Esto permitirá que el cliente vea cómo quedará su proyecto, pruebe los colores y la navegación (prototipo interactivo) y apruebe todo antes de entrar a la fase de desarrollo. Ahorrando tiempo, evitando errores y me posiciona como un consultor integral.",
  },
]);
</script>
