<template>
  <header class="gradient-bg text-white shadow-lg">
    <div class="container mx-auto px-6 py-4">
      <div class="flex justify-between items-center">
        <!-- Logo y nombre -->
        <NuxtLink to="/" >
          <div class="flex items-center space-x-3">
          <div class="w-10 h-10 bg-white rounded-lg flex items-center justify-center">
            <span class="text-[#071793] font-bold text-xl">🏠</span>
          </div>
          <div>
            <h1 class="text-2xl font-bold">InmobiEasy</h1>
            <p class="text-[#A4B5CA] text-sm">Tu hogar ideal está aquí</p>
          </div>
        </div>
        </NuxtLink>

        <!-- Navegación desktop -->
        <nav class="hidden md:flex space-x-8">
          <NuxtLink 
            to="/" 
            class="text-white hover:text-[#E3C39D] transition-colors duration-300 font-medium"
            active-class="text-[#E3C39D] border-b-2 border-[#E3C39D]"
          >
            Inicio
          </NuxtLink>
          <NuxtLink 
            to="/propiedades" 
            class="text-white hover:text-[#eeebe8] transition-colors duration-300 font-medium"
            active-class="text-[#E3C39D] border-b-2 border-[#E3C39D]"
          >
            Propiedades
          </NuxtLink>
          <NuxtLink 
            to="/about" 
            class="text-white hover:text-[#E3C39D] transition-colors duration-300 font-medium"
            active-class="text-[#E3C39D] border-b-2 border-[#E3C39D]"
          >
            Nosotros
          </NuxtLink>
          <NuxtLink 
            to="/contact" 
            class="text-white hover:text-[#E3C39D] transition-colors duration-300 font-medium"
            active-class="text-[#E3C39D] border-b-2 border-[#E3C39D]"
          >
            Contacto
          </NuxtLink>
        </nav>

        <!-- Botón de acción desktop -->
        <div class="hidden md:block">
          <button class="btn-secondary px-6 py-2 rounded-lg font-medium">
            Publicar Propiedad
          </button>
        </div>

        <!-- Menú móvil -->
        <button 
          @click="toggleMenu"
          class="md:hidden text-white p-2 hover:bg-blue-600 hover:bg-opacity-10 rounded-lg transition-colors duration-300"
        >
          <svg 
            class="w-6 h-6" 
            fill="none" 
            stroke="currentColor" 
            viewBox="0 0 24 24"
            :class="{ 'rotate-90': isMenuOpen }"
          >
            <path 
              v-if="!isMenuOpen"
              stroke-linecap="round" 
              stroke-linejoin="round" 
              stroke-width="2" 
              d="M4 6h16M4 12h16M4 18h16"
            ></path>
            <path 
              v-else
              stroke-linecap="round" 
              stroke-linejoin="round" 
              stroke-width="2" 
              d="M6 18L18 6M6 6l12 12"
            ></path>
          </svg>
        </button>
      </div>

      <!-- Menú móvil desplegable -->
      <div 
        v-show="isMenuOpen"
        class="md:hidden mt-4 pb-4 border-t border-white border-opacity-20"
      >
        <nav class="flex flex-col space-y-4 pt-4">
          <NuxtLink 
            to="/" 
            @click="closeMenu"
            class="text-white hover:text-[#E3C39D] transition-colors duration-300 font-medium py-2 px-4 rounded-lg  hover:bg-opacity-10"
            active-class="text-[#E3C39D]  bg-opacity-10"
          >
            🏠 Inicio
          </NuxtLink>
          <NuxtLink 
            to="/propiedades" 
            @click="closeMenu"
            class="text-white hover:text-[#E3C39D] transition-colors duration-300 font-medium py-2 px-4 rounded-lg hover:bg-opacity-10"
            active-class="text-[#E3C39D]  bg-opacity-10"
          >
            🏢 Propiedades
          </NuxtLink>
          <NuxtLink 
            to="/about" 
            @click="closeMenu"
            class="text-white hover:text-[#E3C39D] transition-colors duration-300 font-medium py-2 px-4 rounded-lg  hover:bg-opacity-10"
            active-class="text-[#E3C39D]  bg-opacity-10"
          >
            ℹ️ Nosotros
          </NuxtLink>
          <NuxtLink 
            to="/contact" 
            @click="closeMenu"
            class="text-white hover:text-[#E3C39D] transition-colors duration-300 font-medium py-2 px-4 rounded-lg  hover:bg-opacity-10"
            active-class="text-[#E3C39D]  bg-opacity-10"
          >
            📞 Contacto
          </NuxtLink>
          
          <!-- Botón de acción móvil -->
          <div class="pt-2">
            <button class="btn-secondary w-full py-3 rounded-lg font-medium">
              📝 Publicar Propiedad
            </button>
          </div>
        </nav>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>
