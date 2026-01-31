<template>
  <div class="py-16 px-6">
    <div class="max-w-7xl mx-auto">
      <!-- Header -->
      <div class="mb-16">
        <h1 class="text-5xl font-bold text-white mb-6">Nos Solutions</h1>
        <p class="text-gray-400 text-lg max-w-2xl">
          OrgaAfrica regroupe tout ce dont un restaurant a besoin dans un système unique et
          connecté.
        </p>
      </div>

      <!-- SECTION 1 -->
      <!-- Solutions -->
      <div class="space-y-50">
        <SolutionCard
          v-for="solution in firstSolutions"
          :key="solution.title"
          :title="solution.title"
          :description="solution.description"
        />
      </div>

      <!-- Mobile Mockups -->
      <div
        class="relative flex justify-center items-center transform -translate-y-12/12 -translate-x-10"
      >
        <div class="relative z-20">
          <img src="/Mobile Screen 4.png" alt="OrgaAfrica Mobile App" class="w-auto h-auto" />
        </div>

        <div class="absolute top-12 left-1/2 transform translate-x-20 rotate-1 z-10">
          <img
            src="/Mobile Screen 2.png"
            alt="OrgaAfrica Mobile App"
            class="w-auto h-auto opacity-90"
          />
        </div>
      </div>

      <!-- SECTION 2 -->
      <div class="grid lg:grid-cols-2 items-center gap-12 -mt-8 md:-mt-12">
        <!-- Mobile Mockups (À DROITE) -->
        <div class="relative flex justify-center items-center">
          <!-- Phone principal -->
          <div class="relative z-20">
            <img src="/Mobile Screen 1.png" alt="OrgaAfrica Mobile App" class="w-auto h-auto" />
          </div>

          <!-- Phone secondaire -->
          <div class="absolute z-10 -left-10 top-16 -rotate-1 opacity-90">
            <img
              src="/Mobile Screen 2 (1).png"
              alt="OrgaAfrica Mobile App"
              class="w-auto h-auto transform -translate-x-48 -translate-y-8"
            />
          </div>
        </div>
        <!-- Solutions (À GAUCHE) -->
        <div class="space-y-50">
          <SolutionCard
            v-for="solution in secondSolutions"
            :key="solution.title"
            :title="solution.title"
            :description="solution.description"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import SolutionCard from './SolutionCard.vue'

interface SolutionItem {
  title: string
  description: string
}

const firstSolutions: SolutionItem[] = [
  {
    title: 'Paiements digitaux sécurisés et rapides',
    description:
      'Les paiements en cash sont difficiles à tracer et limitent votre croissance. OrgaAfrica accepte Mobile Money, cartes bancaires et cryptomonnaies, avec une réconciliation simplifiée et des virements rapides, pour une gestion transparente et efficace.',
  },
  {
    title: 'Commandes rapides sans attente',
    description:
      'Les longues files frustrent vos clients et ralentissent le service. Avec notre système de commande via QR code, vos clients passent commande instantanément, suivent leur position en file en temps réel, et peuvent même accéder prioritairement grâce au paiement digital',
  },
]

const secondSolutions: SolutionItem[] = [
  {
    title: 'POS simple et efficace',
    description:
      'Les commandes manuelles causent erreurs et retards qui impactent votre performance. Notre point de vente intuitif vous permet de gérer menus, serveurs, factures instantanées, et fonctionne même hors ligne pour assurer un service fluide à tout moment.',
  },
  {
    title: 'Analyse et reporting clairs',
    description:
      "Sans données fiables, il est difficile d'accéder à des financements ou d'optimiser vos opérations. Nos tableaux de bord vous offrent des analyses précises pour suivre vos ventes, comprendre votre activité et convaincre vos partenaires financiers.",
  },
]
</script>
