<script setup lang="ts">
// Componente de bienvenida para InmobiEasy
</script>

<template>
  <section class="relative overflow-hidden">
    <!-- Hero Section -->
    <div class="gradient-bg text-white py-20">
      <div class="container mx-auto px-6 text-center">
        <h1 class="text-5xl md:text-6xl font-bold mb-6">
          Encuentra tu
          <span class="text-[#E3C39D]">hogar ideal</span>
        </h1>
        <p class="text-xl md:text-2xl text-[#A4B5CA] mb-8 max-w-3xl mx-auto">
          Descubre las mejores propiedades en venta y renta. 
          InmobiEasy te conecta con tu próxima casa de ensueño.
        </p>
        
        <!-- Botones de acción -->
        <div class="flex flex-col sm:flex-row gap-4 justify-center items-center">
          <button class="btn-secondary px-8 py-4 rounded-lg text-lg font-semibold">
            🏠 Ver Propiedades
          </button>
          <button class="bg-white text-[#071793] px-8 py-4 rounded-lg text-lg font-semibold hover:bg-[#CDD5DB] transition-colors duration-300">
            📞 Contactar Agente
          </button>
        </div>
      </div>
    </div>

    <!-- Estadísticas -->
    <div class="bg-white py-16">
      <div class="container mx-auto px-6">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-center">
          <div class="card p-8">
            <div class="text-4xl font-bold text-[#071793] mb-2">500+</div>
            <div class="text-[#4B6382] font-medium">Propiedades Disponibles</div>
          </div>
          <div class="card p-8">
            <div class="text-4xl font-bold text-[#071793] mb-2">1,200+</div>
            <div class="text-[#4B6382] font-medium">Clientes Satisfechos</div>
          </div>
          <div class="card p-8">
            <div class="text-4xl font-bold text-[#071793] mb-2">15+</div>
            <div class="text-[#4B6382] font-medium">Años de Experiencia</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Características destacadas -->
    <div class="bg-[#CDD5DB] py-16">
      <div class="container mx-auto px-6">
        <h2 class="text-3xl font-bold text-center text-[#071793] mb-12">
          ¿Por qué elegir InmobiEasy?
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div class="card p-6 text-center">
            <div class="w-16 h-16 bg-[#071793] rounded-full flex items-center justify-center mx-auto mb-4">
              <span class="text-2xl">🔍</span>
            </div>
            <h3 class="text-xl font-semibold text-[#071793] mb-3">Búsqueda Inteligente</h3>
            <p class="text-[#4B6382]">Filtros avanzados para encontrar exactamente lo que buscas</p>
          </div>
          <div class="card p-6 text-center">
            <div class="w-16 h-16 bg-[#A68868] rounded-full flex items-center justify-center mx-auto mb-4">
              <span class="text-2xl">🤝</span>
            </div>
            <h3 class="text-xl font-semibold text-[#071793] mb-3">Asesoría Personalizada</h3>
            <p class="text-[#4B6382]">Agentes expertos te acompañan en todo el proceso</p>
          </div>
          <div class="card p-6 text-center">
            <div class="w-16 h-16 bg-[#E3C39D] rounded-full flex items-center justify-center mx-auto mb-4">
              <span class="text-2xl">💰</span>
            </div>
            <h3 class="text-xl font-semibold text-[#071793] mb-3">Mejores Precios</h3>
            <p class="text-[#4B6382]">Garantizamos las mejores ofertas del mercado</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

