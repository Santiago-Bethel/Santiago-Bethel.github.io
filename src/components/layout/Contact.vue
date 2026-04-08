<template>
  <section class="mt-32" id="contact">
    <SectionHeader title="Contact Me" />
    <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
      <form @submit.prevent="sendEmail" class="space-y-8">
        <div v-for="(item, index) in inputs" :key="index">
          <Input
            :id="item.id"
            :label="item.label"
            :type="item.type"
            :placeholder="placeholder"
            :rows="rows"
          />
        </div>
        <div class="flex justify-between">
          <Button label="Send" />

          <div class="mt-2 flex justify-center space-x-3 md:space-x-8">
            <a href="https://www.linkedin.com/in/santiago-andres-bethel-ariza-1b1564401/" class="text-gray-600 hover:text-blue-700">
              <Icon icon="fa-brands:linkedin" style="font-size: 2rem" />
            </a>
            <a href="https://github.com/Santiago-Bethel" class="text-gray-600 hover:text-gray-800">
              <Icon icon="fa-brands:github" style="font-size: 2rem" />
            </a>
            <a href="https://www.instagram.com/santiagobethel0/" class="text-gray-600 hover:text-pink-500">
              <Icon icon="fa-brands:instagram" style="font-size: 2rem" />
            </a>
          </div>
        </div>
      </form>
    </div>
  </section>
</template>
<script setup>
import SectionHeader from "@/components/UI/SectionHeader.vue";
import Input from "@/components/UI/Input.vue";
import Button from "@/components/UI/Button.vue";
import { ref } from "vue";
import emailjs from '@emailjs/browser';

const sendEmail = (e) => {

  emailjs.sendForm('service_rk0d41e', 'template_e8puhvy', e.target, 'sNvPdEy6tFoDcuFBB')
    .then(() => {
      alert('¡Mensaje enviado con éxito!');
    }, (error) => {
      alert('Error al enviar: ' + error.text);
    });
};

const inputs = ref([
  {
    id: "email",
    label: "Your email",
    type: "email",
    placeholder: "email@example.com",
    rows: undefined,
  },
  {
    id: "subject",
    label: "Subject",
    type: "text",
    placeholder: "Let us know how we can help you",
    rows: undefined,
  },
  {
    id: "message",
    label: "Message",
    type: "textarea",
    placeholder: "Leave a comment",
    rows: 6,
  },
]);
</script>
