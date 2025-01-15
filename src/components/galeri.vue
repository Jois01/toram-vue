<template>
  <div class="mx-auto max-w-2xl px-4 py-16 sm:px-6 sm:py-24 lg:max-w-7xl lg:px-8">
    <div class="text-5xl font-bold text-center text-gray-900 dark:text-slate-100 my-8">Galeri</div>
    <div class="grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-3 xl:gap-x-8">
      <div
        v-for="galeri in galeris"
        :key="galeri.id"
        @click="openModal(galeri)"
        class="group border border-gray-300 bg-white dark:border-black dark:bg-slate-800 dark:shadow-black shadow-md shadow-gray-300 pb-4 rounded-md p-2 dark:text-slate-100"
      >
        <img :src="galeri.image" class="w-full rounded-lg bg-gray-200" />
        <h3 class="mt-4 text-xl font-bold ml-2">{{ galeri.title }}</h3>
        <div class="mt-1 gap-2 font-medium grid grid-cols-3"></div>
      </div>
    </div>

    <div v-if="modalOpen" class="fixed inset-0 z-10 flex items-center justify-center bg-black bg-opacity-50">
      <div class="bg-white rounded-lg p-4 shadow-lg relative max-w-lg mx-auto">
        <button class="absolute top-2 right-2 text-gray-400 hover:text-gray-900" @click="closeModal">✖</button>
        <div class="content mt-10">
          <img :src="selectedGambar.image" class="w-full rounded-md" />
          <h3 class="mt-4 text-2xl font-bold text-gray-900 text-center">
            {{ selectedGambar.title }}
          </h3>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref } from "vue";

const modalOpen = ref(false);
const selectedGambar = ref(null);
function openModal(galeri) {
  selectedGambar.value = galeri;
  modalOpen.value = true;
}
function closeModal() {
  modalOpen.value = false;
  selectedGambar.value = null;
}
</script>
<script>
import galeris from "../store/galeris.json";
export default {
  data() {
    return {
      galeris,
    };
  },
};
</script>
