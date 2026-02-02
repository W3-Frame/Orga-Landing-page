<template>
  <div class="text-white py-10 sm:py-14 lg:py-16 px-4 sm:px-6 lg:px-8 xl:px-12">
    <!-- Header -->
    <div class="max-w-7xl mx-auto mb-10 sm:mb-12 lg:mb-16">
      <h1 class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-bold mb-2 sm:mb-3">Les Modules de la Plateforme</h1>
      <p class="text-base sm:text-lg text-gray-400 font-semibold">Commandes & Gestion de file d'attente</p>
    </div>

    <!-- Main Content Grid -->
    <div class="flex flex-col lg:flex-row justify-between items-start gap-8 lg:gap-12">
      <!-- Left Column - Modules Info -->
      <div class="w-full lg:w-1/2">
        <div class="space-y-6 sm:space-y-8">
          <div
            v-for="module in modules"
            :key="module.title"
            class="bg-black rounded-2xl sm:rounded-3xl p-5 sm:p-6 border border-zinc-800"
          >
            <h2 class="text-xl sm:text-2xl lg:text-3xl font-semibold mb-2 sm:mb-3">{{ module.title }}</h2>
            <p class="text-[#EFFDF5] text-xs sm:text-sm mb-3 sm:mb-4">{{ module.description }}</p>

            <ul class="space-y-2 sm:space-y-3">
              <li v-for="item in module.items" :key="item" class="flex items-start text-xs sm:text-sm">
                <span class="text-gray-400 mr-2 sm:mr-3 flex-shrink-0">•</span>
                <span class="text-white">{{ item }}</span>
              </li>
            </ul>
          </div>
        </div>
      </div>

      <!-- Right Column - Phone Mockup -->
      <div class="w-full lg:w-1/2 flex justify-center lg:justify-end">
        <div class="relative flex-shrink-0">
          <img src="/public/Rectangle 4221 (2).png" alt="" class="w-full max-w-sm lg:max-w-md" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
interface PlatformModule {
  title: string
  description: string
  items: string[]
}

const modules: PlatformModule[] = [
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
