<template>
  <nav class="bg-[#8C8B8B] mx-10 my-8 py-6 px-5 rounded-2xl">
    <div class="max-w-7xl mx-auto flex items-center justify-between">
      <div class="text-2xl font-bold text-white tracking-tight">OrgaAfrica</div>

      <div class="text-white text-base font-normal flex item-center gap-10">
        <a href="#" class="py-2 hover:border-t-2 hover:border-b-2 hover:border-white transition-all"
          >Accueil</a
        >
        <a href="#" class="py-2 hover:border-t-2 hover:border-b-2 hover:border-white transition-all"
          >Nos services</a
        >
        <a href="#" class="py-2 hover:border-t-2 hover:border-b-2 hover:border-white transition-all"
          >Solution</a
        >
        <a href="#" class="py-2 hover:border-t-2 hover:border-b-2 hover:border-white transition-all"
          >Qui somme nous ?</a
        >
      </div>

      <div class="flex items-center gap-8">
        <div
          class="text-white text-base font-medium cursor-pointer hover:opacity-80 transition-opacity flex items-center gap-2"
        >
          FR
          <svg
            width="12"
            height="8"
            viewBox="0 0 12 8"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path d="M1 1L6 6L11 1" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
          </svg>
        </div>
        <button
          class="bg-red-500 hover:bg-red-600 transition-colors text-white px-8 py-3.5 rounded-lg text-base font-medium"
        >
          Demander une démo
        </button>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts"></script>
