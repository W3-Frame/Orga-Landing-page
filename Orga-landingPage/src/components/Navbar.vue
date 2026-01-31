<template>
  <nav class="bg-[#8C8B8B] mx-10 my-8 py-4 px-5 rounded-2xl">
    <div class="max-w-7xl mx-auto flex items-center justify-between">
      <div class="text-3xl font-extrabold text-white tracking-tight">OrgaAfrica</div>

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
        <div class="relative">
          <button
            type="button"
            @click="toggleLanguageMenu"
            class="text-white text-base font-medium cursor-pointer hover:opacity-80 transition-opacity flex items-center gap-2"
            aria-haspopup="listbox"
            :aria-expanded="isLanguageOpen"
          >
            {{ selectedLanguage }}
            <svg
              width="12"
              height="8"
              viewBox="0 0 12 8"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
              :class="isLanguageOpen ? 'rotate-180' : 'rotate-0'"
              class="transition-transform"
            >
              <path
                d="M1 1L6 6L11 1"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
              />
            </svg>
          </button>

          <div
            v-if="isLanguageOpen"
            class="absolute right-0 mt-2 w-28 rounded-xl bg-[#6f6e6e] border border-white/10 shadow-lg py-2 z-10"
            role="listbox"
          >
            <button
              v-for="lang in languages"
              :key="lang"
              type="button"
              @click.stop="selectLanguage(lang)"
              class="w-full px-3 py-2 text-left text-white text-sm hover:bg-white/10 transition-colors"
              :class="lang === selectedLanguage ? 'font-semibold' : 'font-normal'"
              role="option"
              :aria-selected="lang === selectedLanguage"
            >
              {{ lang }}
            </button>
          </div>
        </div>
        <button
          class="bg-red-500 hover:bg-red-600 transition-colors text-white px-8 py-3.5 rounded-xl text-base font-medium"
        >
          Demander une démo
        </button>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue'

const languages = ['FR', 'EN'] as const
const selectedLanguage = ref<(typeof languages)[number]>('FR')
const isLanguageOpen = ref(false)

const toggleLanguageMenu = (event: MouseEvent) => {
  event.stopPropagation()
  isLanguageOpen.value = !isLanguageOpen.value
}

const selectLanguage = (lang: (typeof languages)[number]) => {
  selectedLanguage.value = lang
  isLanguageOpen.value = false
}

const closeLanguageMenu = () => {
  isLanguageOpen.value = false
}

onMounted(() => {
  window.addEventListener('click', closeLanguageMenu)
})

onBeforeUnmount(() => {
  window.removeEventListener('click', closeLanguageMenu)
})
</script>
<style scoped></style>
