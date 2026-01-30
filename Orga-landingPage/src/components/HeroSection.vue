<script setup lang="ts"></script>

<template>
  <section
    class="min-h-screen bg-black px-8 py-20 flex items-center justify-center relative overflow-hidden"
  >
    <div class="max-w-6xl w-full">
      <!-- Badge utilisateurs -->
      <div class="flex justify-center mb-12">
        <div>
          <img src="/Container.png" alt="users" />
        </div>
      </div>

      <!-- Titre et description -->
      <div class="text-center mb-16 relative z-10">
        <h1 class="text-5xl lg:text-6xl font-bold text-white mb-8 leading-tight">
          OrgaAfrica propose deux solutions formant le système d’exploitation des restaurants et
          points de vente en Afrique.
        </h1>

        <p class="text-lg text-gray-300 mb-12 max-w-3xl mx-auto leading-relaxed">
          Gérez commandes, paiements, files d'attente, réservations, fidélité et croissance sur une
          seule plateforme, pensée pour l'Afrique
        </p>

        <div class="flex gap-6 justify-center mb-20 flex-col sm:flex-row">
          <button
            class="bg-red-500 transition-all text-white px-3 rounded-2xl text-lg font-medium transform hover:scale-105 hover:shadow-lg"
          >
            Demander une démo
          </button>
          <button
            class="bg-transparent transition-all text-white border-1 border-red-500 px-10 py-4 rounded-2xl text-lg font-medium transform hover:scale-105 hover:shadow-lg"
          >
            Commencer gratuitement
          </button>
        </div>
      </div>
      <!-- Images des téléphones -->
      <div class="flex justify-center items-center gap-12 mt-24 flex-wrap relative z-10">
        <!-- Left Phone -->
        <div class="relative w-80 -rotate-12 drop-shadow-2xl">
          <img
            src="/public/Rectangle 4223.png"
            alt="Orga App Left"
            class="w-full h-auto transform -translate-y-8/12"
          />
        </div>
        <!-- <div>
          <img src="/public/Frame 33.png" alt="" />
          <img src="/public/Frame 33.png" alt="" />
        </div> -->

        <!-- Right Phone -->
        <div class="relative w-80 rotate-12 drop-shadow-2xl">
          <img
            src="/phoneG.png"
            alt="Orga App Right"
            class="w-full h-auto transform -translate-y-8/12 translate-x-5"
          />
        </div>
      </div>
    </div>
  </section>
</template>
