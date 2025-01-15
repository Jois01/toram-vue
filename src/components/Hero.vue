<template>
  <div class="mx-auto mt-10 md:mt-0 grid max-w-2xl grid-cols-1 text-gray-900 dark:text-slate-100 items-center gap-20 px-4 sm:px-6 sm:py-32 lg:max-w-7xl lg:grid-cols-2 lg:px-8" v-for="profile in profiles">
    <div>
      <div class="text-3xl font-bold sm:text-5xl">
        {{ profile.salam }} {{ profile.name }}
      </div>
      <div class="text-3xl font-bold sm:text-5xl my-2">{{ profile.job }}</div>
      <div class="mt-4 text-xl"></div>
    </div>
    <!-- Gambar Profile -->
    <div class="image flex justify-center items-center sm:w-80 w-56 mx-auto">
      <div class="profile">
        <img :src="profile.image" :alt="profile.alt" class="block rounded-t-lg" />
        <div class="text-lg font-bold sm:w-80 w-56 bg-gray-800 dark:bg-gray-100 text-white dark:text-gray-900 text-center py-2 rounded-b-md">
          {{ profile.name }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const profiles = [
  {
    salam: "Halo ges gw ",
    job: "Katana user",
    name: "Blue Zero",
    image: "elJamet1.jpg",
    alt: "profile photo",
  },
];
</script>
