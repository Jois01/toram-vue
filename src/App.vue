<script setup>
import Navbar from './components/Navbar.vue'
import hero from './components/hero.vue'
import about from './components/about.vue'
import galeri from './components/galeri.vue'
import akhir from './components/akhir.vue'
</script>

<template>
  <Navbar />
  <div id="home">
    <hero />
  </div>
  <div id="about">
    <about />
  </div>
  <div id="galeri">
    <galeri />
  </div>
  <akhir />
</template>
