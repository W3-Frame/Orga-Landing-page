<script setup lang="ts">
interface ProfileSolution {
  title: string
  description: string
  inlineText: boolean
}

const profileSolutions: ProfileSolution[] = [
  {
    title: 'Pour les restaurants :',
    description: "Augmentez vos revenus, réduisez l'attente et reprenez le contrôle.",
    inlineText: true,
  },
  {
    title: 'Pour les vendeurs & commerçants informels :',
    description: 'Passez au digital sans matériel ni complexité.',
    inlineText: false,
  },
  {
    title: 'Pour les entreprises :',
    description: 'Offrez des avantages repas intelligents et maîtrisez les dépenses.',
    inlineText: false,
  },
]
</script>

<template>
  <div class="bg-black text-white py-16 px-8">
    <div class="max-w-7xl mx-auto">
      <h1 class="text-5xl font-bold mb-16">Solutions par profil</h1>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-32 items-center">
        <div class="w-auto h-auto bg-[#FC0A02] rounded-4xl">
          <img src="/public/Rectangle 4221.png" alt="" />
        </div>

        <div class="space-y-6">
          <div
            v-for="profile in profileSolutions"
            :key="profile.title"
            class="bg-zinc-900 border border-zinc-800 rounded-2xl p-6 hover:border-zinc-700 transition-all"
          >
            <div class="flex items-start gap-4">
              <div v-if="profile.inlineText">
                <div class="bg-red-600 rounded-full w-10 h-10 flex items-center justify-center">
                  <span class="text-white font-bold text-xl">8</span>
                </div>
              </div>
              <div
                v-else
                class="bg-red-600 rounded-full w-10 h-10 flex items-center justify-center"
              >
                <span class="text-white font-bold text-xl">8</span>
              </div>

              <div v-if="profile.inlineText">
                <h3 class="text-xl font-bold mb-2">{{ profile.title }}</h3>
                <p class="text-gray-300 leading-relaxed">{{ profile.description }}</p>
              </div>
            </div>

            <div v-if="!profile.inlineText">
              <h3 class="text-xl font-bold mb-2">{{ profile.title }}</h3>
              <p class="text-gray-300 leading-relaxed">{{ profile.description }}</p>
            </div>
          </div>

          <button
            class="bg-red-600 hover:bg-red-700 text-white font-bold py-4 px-8 rounded-xl transition-colors text-lg shadow-lg shadow-red-900/50"
          >
            Télécharger
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
