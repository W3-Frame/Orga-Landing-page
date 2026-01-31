<template>
  <nav
    class="bg-[#8C8B8B] mx-3 sm:mx-6 lg:mx-10 my-4 sm:my-6 lg:my-8 py-3 lg:py-4 px-4 lg:px-5 rounded-2xl"
  >
    <div class="max-w-7xl mx-auto flex items-center justify-between">
      <!-- ===== LOGO ===== -->
      <div
        class="text-2xl sm:text-3xl lg:text-5xl font-extrabold text-white tracking-tight flex-shrink-0"
      >
        OrgaAfrica
      </div>

      <!-- ===== LINKS DESKTOP (caché sur mobile) ===== -->
      <div class="hidden lg:flex text-white text-base font-normal items-center gap-10">
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

      <!-- ===== ACTIONS DESKTOP (caché sur mobile) ===== -->
      <div class="hidden lg:flex items-center gap-8">
        <!-- Language Switcher -->
        <div class="relative">
          <button
            type="button"
            @click.stop="toggleLanguageMenu"
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
              class="transition-transform duration-200"
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

        <!-- CTA Desktop -->
        <button
          class="bg-red-500 hover:bg-red-600 transition-colors text-white px-8 py-3.5 rounded-xl text-base font-medium"
        >
          Demander une démo
        </button>
      </div>

      <!-- ===== HAMBURGER (visible sur mobile uniquement) ===== -->
      <button
        type="button"
        @click.stop="toggleMobileMenu"
        class="lg:hidden flex flex-col justify-center items-center w-10 h-10 gap-[5px] cursor-pointer"
        aria-label="Menu"
        :aria-expanded="isMobileOpen"
      >
        <!-- Barre 1 -->
        <span
          class="block h-[2px] bg-white rounded-full transition-all duration-300 ease-in-out"
          :class="isMobileOpen ? 'w-5 rotate-45 translate-y-[7px]' : 'w-6'"
        ></span>
        <!-- Barre 2 (disparaît quand ouvert) -->
        <span
          class="block h-[2px] bg-white rounded-full transition-all duration-300 ease-in-out"
          :class="isMobileOpen ? 'w-0 opacity-0' : 'w-6 opacity-100'"
        ></span>
        <!-- Barre 3 -->
        <span
          class="block h-[2px] bg-white rounded-full transition-all duration-300 ease-in-out"
          :class="isMobileOpen ? 'w-5 -rotate-45 -translate-y-[7px]' : 'w-6'"
        ></span>
      </button>
    </div>

    <!-- ===== MENU MOBILE DÉROULANT ===== -->
    <!--
      Technique : on contrôle max-height + opacity pour une animation fluide
      en CSS sans JS forcé. max-h-0 → max-h-[400px] avec transition.
    -->
    <div
      @click.stop
      class="lg:hidden overflow-hidden transition-all duration-300 ease-in-out"
      :class="isMobileOpen ? 'max-h-[400px] opacity-100 mt-3' : 'max-h-0 opacity-0 mt-0'"
    >
      <!-- Séparateur -->
      <div class="border-t border-white/20 mb-3"></div>

      <!-- Links -->
      <div class="flex flex-col gap-1">
        <a
          href="#"
          @click="closeMobileMenu"
          class="text-white text-base font-normal px-3 py-2.5 rounded-lg hover:bg-white/10 transition-colors"
          >Accueil</a
        >
        <a
          href="#"
          @click="closeMobileMenu"
          class="text-white text-base font-normal px-3 py-2.5 rounded-lg hover:bg-white/10 transition-colors"
          >Nos services</a
        >
        <a
          href="#"
          @click="closeMobileMenu"
          class="text-white text-base font-normal px-3 py-2.5 rounded-lg hover:bg-white/10 transition-colors"
          >Solution</a
        >
        <a
          href="#"
          @click="closeMobileMenu"
          class="text-white text-base font-normal px-3 py-2.5 rounded-lg hover:bg-white/10 transition-colors"
          >Qui somme nous ?</a
        >
      </div>

      <!-- Séparateur -->
      <div class="border-t border-white/20 my-3"></div>

      <!-- Language + CTA groupés en bas -->
      <div class="flex items-center justify-between px-3 pb-2">
        <!-- Language Switcher Mobile -->
        <div class="relative">
          <button
            type="button"
            @click.stop="toggleLanguageMenu"
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
              class="transition-transform duration-200"
            >
              <path
                d="M1 1L6 6L11 1"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
              />
            </svg>
          </button>

          <!-- Dropdown language mobile (s'ouvre vers le haut) -->
          <div
            v-if="isLanguageOpen"
            class="absolute bottom-full left-0 mb-2 w-28 rounded-xl bg-[#6f6e6e] border border-white/10 shadow-lg py-2 z-10"
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

        <!-- CTA Mobile -->
        <button
          @click="closeMobileMenu"
          class="bg-red-500 hover:bg-red-600 transition-colors text-white px-5 py-2.5 rounded-xl text-sm font-medium"
        >
          Demander une démo
        </button>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from 'vue'

// ─── Language switcher ───────────────────────────────
const languages = ['FR', 'EN'] as const
const selectedLanguage = ref<(typeof languages)[number]>('FR')
const isLanguageOpen = ref(false)

const toggleLanguageMenu = () => {
  isLanguageOpen.value = !isLanguageOpen.value
}

const selectLanguage = (lang: (typeof languages)[number]) => {
  selectedLanguage.value = lang
  isLanguageOpen.value = false
}

// ─── Mobile menu ─────────────────────────────────────
const isMobileOpen = ref(false)

const toggleMobileMenu = () => {
  isMobileOpen.value = !isMobileOpen.value
  // Si on ouvre le menu mobile, on ferme le language dropdown
  isLanguageOpen.value = false
}

const closeMobileMenu = () => {
  isMobileOpen.value = false
  isLanguageOpen.value = false
}

// ─── Click outside → fermer tout ─────────────────────
const handleClickOutside = (event: Event) => {
  // Ne pas fermer si on clique sur la navbar elle-même
  const target = event.target as HTMLElement
  if (target.closest('nav')) {
    return
  }
  isLanguageOpen.value = false
  isMobileOpen.value = false
}

onMounted(() => {
  window.addEventListener('click', handleClickOutside)
})

onBeforeUnmount(() => {
  window.removeEventListener('click', handleClickOutside)
})
</script>
