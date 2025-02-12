<template>
  <div class="container mx-auto px-5 lg:px-8 pt-16 pb-24">
    <div class="text-center" id="accordion-title">
      <h5
        class="text-lightBlue tracking-wider mb-3 md:text-base lg:text-lg font-semibold text-sm font-Sawa"
      >
        FORUM ANSWER AND QUESTION
      </h5>
      <h1
        class="text-secondBlack text-2xl font-semibold md:text-3xl xl:max-w-md mx-auto xl:leading-relaxed lg:text-4xl font-Inter mb-5"
      >
        FAQ 
      </h1>
      <p
        class="text-secondGray font-Sawa text-base md:max-w-md mx-auto lg:text-xl md:text-lg mb-8"
      >
        Apa yang kamu tunggu? Gunakan panel Pterodactyl untuk manajemen server yang lebih optimal! Selain itu, kami juga menyediakan layanan encrypt script, remark script, script bot WhatsApp MD, serta berbagai produk digital berkualitas lainnya.
      </p>
    </div>
    <div
      class="grid grid-cols-1 max-w-4xl cursor-pointer mx-auto"
      id="accordions"
    >
      <div v-for="(item, index) in accordionItems" :key="index">
        <div
          class="p-5 border-[1px]"
          :class="{
            'border-paleBlue': item.show,
            'border-secondGray/40': !item.show,
          }"
          v-auto-animate
          @click="toggleAccordion(index)"
        >
          <div
            class="flex items-center justify-between"
            :class="{ 'mb-5': item.show, 'mb-0': !item.show }"
          >
            <div class="flex items-center gap-3">
              <span class="text-base md:text-lg text-paleBlue">&bull;</span>
              <p
                class="text-paleBlue md:text-lg text-base font-semibold font-Inter"
              >
                {{ item.title }}
              </p>
            </div>
            <i
              class="fa-solid"
              :class="{
                'fa-chevron-down text-paleBlue': !item.show,
                'fa-chevron-up text-secondGray/75': item.show,
              }"
            ></i>
          </div>
          <p
            class="text-base md:text-lg text-paleBlue font-Sawa"
            v-if="item.show"
          >
            {{ item.content }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import gsap from "gsap";
const accordionItems = ref([
  {
    title: "Apa itu panel Pterodactyl?",
    content:
      "Pterodactyl adalah panel manajemen server open-source yang dirancang khusus untuk mengelola server game dan aplikasi lainnya. Dengan antarmuka berbasis web yang user-friendly, Pterodactyl mempermudah pengelolaan server tanpa harus menggunakan command line secara langsung.",
    show: false,
  },
  {
    title: "Bagaimana cara menginstal Pterodactyl?",
    content:
      "Menyiapkan server dengan sistem operasi berbasis Linux (Ubuntu/Debian lebih direkomendasikan).  Menginstal Docker & dependencies yang dibutuhkan. Menginstal panel Pterodactyl dengan menjalankan. perintah yang tersedia di dokumentasi resminya. Menambahkan daemon Wings agar server dapat dikelola dengan baik. Mengonfigurasi server & database sesuai kebutuhan.",
    show: false,
  },
  {
    title: "Apa saja fitur unggulan dari Pterodactyl?",
    content:
      "Manajemen server berbasis web dengan tampilan yang mudah digunakan. Dukungan multi-user untuk mengelola server dengan tim. Isolasi server menggunakan Docker untuk keamanan yang lebih baik. API yang kuat, memungkinkan integrasi dengan sistem lain. Dukungan untuk berbagai jenis server seperti Minecraft, Whatsapp Bot, FiveM, dan lainnya.",
    show: false,
  },
  {
    title: "Apa itu Script Bot WhatsApp MD?",
    content: "Script Bot WhatsApp MD adalah kode yang memungkinkan kamu membuat bot WhatsApp Multi-Device (MD) yang bisa berjalan di WhatsApp Web menggunakan Baileys atau library serupa. Bot ini bisa menjalankan perintah otomatis seperti autoreply, download media, dan lainnya.",
    show: false,
  },
  {
    title: "Apa itu encrypt script?",
    content: "Encrypt script adalah proses mengamankan kode sumber dengan cara mengubahnya menjadi bentuk yang lebih sulit dibaca oleh manusia, sehingga sulit untuk dicuri atau dimodifikasi oleh pihak yang tidak berwenang.",
    show: false,
  },
  {
    title: "Apa itu remark script?",
    content:
      "Remark script adalah proses pembersihan dan perbaikan kode dengan menambahkan komentar, merapikan struktur, serta meningkatkan efisiensi tanpa mengubah fungsionalitasnya.",
    show: false,
  },
]);
const toggleAccordion = (index) => {
  accordionItems.value.forEach((item, i) => {
    item.show = i === index ? !item.show : false;
  });
};
onMounted(() => {
  gsap.from("#accordion-title", {
    opacity: 0,
    y: 120,
    duration: 1,
    ease: "slow",
    scrollTrigger: {
      trigger: "#accordion-title",
      once: true,
      start: "top center",
      scrub: 1,
      end: "+=100",
    },
  });
  gsap.from("#accordions", {
    opacity: 0,
    y: 120,
    duration: 1,
    ease: "slow",
    scrollTrigger: {
      trigger: "#accordions",
      once: true,
      start: "top center",
      scrub: 1,
      end: "+=160",
    },
  });
});
</script>
