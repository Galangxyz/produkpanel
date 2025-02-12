<template>
  <section
    class="bg-gradient-to-b from-linearBlue/40 via-white pb-10 to-linearBlue/40"
  >
    <Header></Header>
    <Hero :hero-images="heroImages"></Hero>
  </section>
  <section>
    <Mission :about-image="aboutImage"></Mission>

    <PetList :pet-images="petImages"></PetList>

    <Sponsors :sponsor-details="sponsorDetails"></Sponsors>
  </section>
  <section
    class="bg-gradient-to-b from-linearBlue/40 via-white to-linearBlue/40"
  >
    <Accordion></Accordion>
    <Footer></Footer>
  </section>
</template>

<script setup>
import Header from "./components/HeaderPage.vue";
import Hero from "./components/HeroPage.vue";
import Mission from "./components/MissionPage.vue";
import PetList from "./components/PetList.vue";
import dogscats from "./assets/three pets.png";
import Footer from "./components/Footer.vue";
import Accordion from "./components/Accordion.vue";
import Sponsors from "./components/SponsorPage.vue";
import sponsorImg from "./assets/image 15.jpg";
import heroImage from "./assets/adopt hero.png";
import logo1 from "./assets/logo1.svg";
import logo2 from "./assets/logo2.svg";
import logo3 from "./assets/logo3.svg";
import logo4 from "./assets/logo4.svg";
import panel1 from "./assets/panel1.jpg";
import panel2 from "./assets/panel2.jpg";
import panel3 from "./assets/panel3.jpg";
import panel4 from "./assets/panel4.jpg";

import script1 from "./assets/script1.jpg";
import script2 from "./assets/script2.jpg";
import script3 from "./assets/script3.jpg";
import script4 from "./assets/script4.jpg";
const heroImages = [
  {
    src: heroImage,
    alt: "hero image",
  },
  {
    src: logo1,
    alt: "logo 1",
  },
  {
    src: logo2,
    alt: "logo 2",
  },
  {
    src: logo3,
    alt: "logo 3",
  },
  {
    src: logo4,
    alt: "logo 4",
  },
];
const aboutImage = [
  {
    src: dogscats,
    alt: "dogscats image",
    titleHeader: "About Panel Pterodactyl",
    title: " Performa Stabil, Garansi Aman",
    desc: "Didesain khusus untuk kebutuhan server hosting yang stabil, mudah digunakan, dan efisien dalam manajemen sumber daya.",
    communityHeader: "Profit Use Panel Pterodactyl",
    communityTitle: "Kelola Server Tanpa Ribet",
    communityDesc:
      "Dapatkan kemudahan dalam mengelola server game, bot, dan berbagai aplikasi dengan sistem yang efisien dan scalable.",
    countOne: 50,
    countOneDetail: "Server Aktif",
    countTwo: 70,
    countTwoDetail: "Pengguna Terdaftar",
    countThree: 90,
    countThreeDetail: "Jam Dukungan Teknis",
  },
];
const petImages = [
  // Panel
  {
    src: panel1,
    alt: "panel",
    name: "Ram 1Gb",
    old: "Garansi 14 Days",
    waiting: "Rp.2.000",
  },
  {
    src: panel2,
    alt: "panel",
    name: "Ram 2Gb",
    old: "Garansi 14 Days",
    waiting: "Rp.3.000",
  },
  {
    src: panel3,
    alt: "panel",
    name: "Ram 3Gb",
    old: "Garansi 14 Days",
    waiting: "Rp.4.000",
  },
  {
    src: panel4,
    alt: "panel",
    name: "Ram Unlimited",
    old: "Garansi 14 Day",
    waiting: "Rp.5.000",
  },

  // Script
  {
    src: script4,
    alt: "script",
    name: "Egg Support Console",
    old: "Full Instalasi",
    waiting: "Rp.5.000",
  },
  {
    src: script1,
    alt: "script",
    name: "Tokoh Api Script",
    old: "Version 1.0",
    waiting: "Rp.20.000",
  },
  {
    src: script2,
    alt: "script",
    name: "Create Panel Script",
    old: "Version 1.0",
    waiting: "Rp.15.000",
  },
  {
    src: script3,
    alt: "script",
    name: "Jasa Install Pterodactyl",
    old: "Full Instalasi",
    waiting: "Rp.10.000",
  },
];
const sponsorDetails = [
  {
    src: sponsorImg,
    alt: "sponsor img",
    titleHead: "Encrypt && Remark",
    title: "JASA ENCRYPT & REMARK SCRIPT",
    desc: "Dapatkan jasa encrypt dan remark script dengan harga terjangkau, memastikan keamanan serta efisiensi terbaik untuk kebutuhan Anda.",
    button: "Order now",
  },
];
</script>
