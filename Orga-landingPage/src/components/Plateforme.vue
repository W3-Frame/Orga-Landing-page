<template>
  <div class="min-h-screen bg-black text-white py-16 px-6 md:px-12 lg:px-20">
    <!-- Header -->
    <div class="max-w-7xl mx-auto mb-12">
      <h1 class="text-4xl md:text-5xl font-bold mb-3">Les Modules de la Plateforme</h1>
      <p class="text-lg text-gray-400">Commandes & Gestion de file d'attente</p>
    </div>

    <!-- Main Content Grid -->
    <div class="mx-auto grid grid-cols-1 lg:grid-cols-2 gap-12 items-start">
      <!-- Left Column - Modules Info -->
      <div class="space-y-8">
        <div
          v-for="module in modules"
          :key="module.title"
          class="bg-zinc-900/50 rounded-3xl p-6 border border-zinc-800 w-[600px]"
        >
          <h2 class="text-2xl font-semibold mb-3">{{ module.title }}</h2>
          <p class="text-gray-400 text-sm mb-4">{{ module.description }}</p>

          <ul class="space-y-3">
            <li v-for="item in module.items" :key="item" class="flex items-start text-sm">
              <span class="text-gray-400 mr-3">•</span>
              <span class="text-gray-300">{{ item }}</span>
            </li>
          </ul>
        </div>
      </div>

      <!-- Right Column - Phone Mockup -->
      <div class="flex justify-center lg:justify-end">
        <div class="relative">
          <!-- Phone Frame -->

          <img src="/iPhone-13-Pro-Front.png" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const modules = [
  {
    title: "Commandes & Gestion de file d'attente",
    description: 'Permettez aux clients de commander sans attendre.',
    items: [
      'Scan de QR code',
      'Position en temps réel dans la file',
      'Suivi de commande',
      'Accès prioritaire via paiement digital',
    ],
  },
  {
    title: 'Infrastructure Paiements',
    description: 'Acceptez tous les moyens de paiement utilisés par vos clients',
    items: [
      'Mobile Money (Flooz, TMoney, Mix…)',
      'Cartes bancaires',
      'Cryptomonnaies',
      'Réconciliation du cash',
      'Virements rapides (J+1 / J+3)',
    ],
  },
]
</script>

<style scoped>
/* Animations et effets supplémentaires si nécessaire */
</style>
