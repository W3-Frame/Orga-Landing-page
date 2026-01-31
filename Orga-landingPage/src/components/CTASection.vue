<script setup lang="ts">
import StoreButtons from './StoreButtons.vue'
</script>

<template>
  <section class="relative bg-black text-white px-6 md:px-12 lg:px-24 overflow-hidden">
    <div class="absolute inset-0 opacity-20">
      <div class="absolute -top-40 -right-40 w-96 h-96 bg-red-500 rounded-full blur-3xl"></div>
      <div class="absolute top-1/2 -left-40 w-80 h-80 bg-red-600 rounded-full blur-3xl"></div>
    </div>

    <div class="relative max-w-7xl mx-auto">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <div class="">
          <h2 class="text-5xl md:text-6xl font-bold mb-6 leading-tight">
            Prêt à moderniser votre restaurant ?
          </h2>
          <p class="text-xl text-gray-300 mb-8">Demandez une démo dès aujourd'hui.</p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center items-center">
            <StoreButtons class="flex flex-col sm:flex-row gap-3 sm:gap-4 pt-6" />
            <div>
              <button
                class="bg-red-600 hover:bg-red-700 text-white font-bold py-1 px-5 rounded-lg transition-all duration-300 transform hover:scale-105"
              >
                Demander une démo
              </button>
            </div>
          </div>
        </div>

        <div>
          <img src="/public/image 19.png" alt="" />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
