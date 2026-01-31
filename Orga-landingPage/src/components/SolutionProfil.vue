<script setup lang="ts"></script>

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
            class="bg-zinc-900 border border-zinc-800 rounded-2xl p-6 hover:border-zinc-700 transition-all"
          >
            <div class="flex items-start gap-4">
              <div class="">
                <div class="bg-red-600 rounded-full w-10 h-10 flex items-center justify-center">
                  <span class="text-white font-bold text-xl">8</span>
                </div>
              </div>
              <div>
                <h3 class="text-xl font-bold mb-2">Pour les restaurants :</h3>
                <p class="text-gray-300 leading-relaxed">
                  Augmentez vos revenus, réduisez l'attente et reprenez le contrôle.
                </p>
              </div>
            </div>
          </div>

          <div
            class="bg-zinc-900 border border-zinc-800 rounded-2xl p-6 hover:border-zinc-700 transition-all"
          >
            <div class="flex items-start gap-4">
              <div class="bg-red-600 rounded-full w-10 h-10 flex items-center justify-center">
                <span class="text-white font-bold text-xl">8</span>
              </div>
            </div>
            <div>
              <h3 class="text-xl font-bold mb-2">Pour les vendeurs & commerçants informels :</h3>
              <p class="text-gray-300 leading-relaxed">
                Passez au digital sans matériel ni complexité.
              </p>
            </div>
          </div>

          <div
            class="bg-zinc-900 border border-zinc-800 rounded-2xl p-6 hover:border-zinc-700 transition-all"
          >
            <div class="flex items-start gap-4">
              <div class="bg-red-600 rounded-full w-10 h-10 flex items-center justify-center">
                <span class="text-white font-bold text-xl">8</span>
              </div>
            </div>
            <div>
              <h3 class="text-xl font-bold mb-2">Pour les entreprises :</h3>
              <p class="text-gray-300 leading-relaxed">
                Offrez des avantages repas intelligents et maîtrisez les dépenses.
              </p>
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
