<template>
  <div class="min-h-screen bg-[#CDD5DB]">
    <!-- Hero Section -->
    <section class="relative overflow-hidden">
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

    <!-- Sección de búsqueda -->
    <div class="bg-white shadow-lg py-8">
      <div class="container mx-auto px-6">
        <h2 class="text-3xl font-bold text-[#071793] mb-6 text-center">
          Busca tu propiedad ideal
        </h2>
        
        <!-- Filtros de búsqueda -->
        <div class="grid grid-cols-1 md:grid-cols-4 gap-4 max-w-4xl mx-auto">
          <div>
            <label class="block text-[#4B6382] font-medium mb-2">Tipo de Propiedad</label>
            <select class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]">
              <option>Todas</option>
              <option>Casa</option>
              <option>Departamento</option>
              <option>Oficina</option>
              <option>Terreno</option>
            </select>
          </div>
          
          <div>
            <label class="block text-[#4B6382] font-medium mb-2">Ubicación</label>
            <input 
              type="text" 
              placeholder="Ciudad, colonia..."
              class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
            >
          </div>
          
          <div>
            <label class="block text-[#4B6382] font-medium mb-2">Precio Máximo</label>
            <select class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]">
              <option>Sin límite</option>
              <option>$500,000</option>
              <option>$1,000,000</option>
              <option>$2,000,000</option>
              <option>$5,000,000</option>
            </select>
          </div>
          
          <div class="flex items-end">
            <button class="btn-primary w-full py-3 rounded-lg font-semibold">
              🔍 Buscar
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Propiedades destacadas -->
    <div class="container mx-auto px-6 py-12">
      <h3 class="text-2xl font-bold text-[#071793] mb-8">Propiedades Destacadas</h3>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Propiedad 1 -->
        <div class="card overflow-hidden">
          <div class="h-48 bg-gradient-to-br from-[#A4B5CA] to-[#4B6382] flex items-center justify-center">
            <span class="text-6xl">🏠</span>
          </div>
          <div class="p-6">
            <div class="flex justify-between items-start mb-3">
              <h4 class="text-xl font-semibold text-[#071793]">Casa Moderna en Polanco</h4>
              <span class="bg-[#E3C39D] text-[#071793] px-3 py-1 rounded-full text-sm font-medium">Venta</span>
            </div>
            <p class="text-[#4B6382] mb-4">Hermosa casa de 3 recámaras, 2 baños, cocina equipada y jardín privado.</p>
            <div class="flex justify-between items-center">
              <span class="text-2xl font-bold text-[#A68868]">$2,500,000</span>
              <button class="btn-primary px-4 py-2 rounded-lg text-sm">
                Ver Detalles
              </button>
            </div>
          </div>
        </div>

        <!-- Propiedad 2 -->
        <div class="card overflow-hidden">
          <div class="h-48 bg-gradient-to-br from-[#E3C39D] to-[#A68868] flex items-center justify-center">
            <span class="text-6xl">🏢</span>
          </div>
          <div class="p-6">
            <div class="flex justify-between items-start mb-3">
              <h4 class="text-xl font-semibold text-[#071793]">Departamento en Condesa</h4>
              <span class="bg-[#A4B5CA] text-[#071793] px-3 py-1 rounded-full text-sm font-medium">Renta</span>
            </div>
            <p class="text-[#4B6382] mb-4">Departamento de lujo con vista panorámica, amenidades premium y seguridad 24/7.</p>
            <div class="flex justify-between items-center">
              <span class="text-2xl font-bold text-[#A68868]">$25,000/mes</span>
              <button class="btn-primary px-4 py-2 rounded-lg text-sm">
                Ver Detalles
              </button>
            </div>
          </div>
        </div>

        <!-- Propiedad 3 -->
        <div class="card overflow-hidden">
          <div class="h-48 bg-gradient-to-br from-[#071793] to-[#4B6382] flex items-center justify-center">
            <span class="text-6xl">🏡</span>
          </div>
          <div class="p-6">
            <div class="flex justify-between items-start mb-3">
              <h4 class="text-xl font-semibold text-[#071793]">Casa Familiar en Lomas</h4>
              <span class="bg-[#E3C39D] text-[#071793] px-3 py-1 rounded-full text-sm font-medium">Venta</span>
            </div>
            <p class="text-[#4B6382] mb-4">Casa familiar de 4 recámaras con amplio jardín, alberca y cochera para 3 autos.</p>
            <div class="flex justify-between items-center">
              <span class="text-2xl font-bold text-[#A68868]">$4,200,000</span>
              <button class="btn-primary px-4 py-2 rounded-lg text-sm">
                Ver Detalles
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Botón ver más -->
      <div class="text-center mt-12">
        <button class="btn-secondary px-8 py-3 rounded-lg text-lg font-semibold">
          Ver Todas las Propiedades
        </button>
      </div>
    </div>

    <!-- Sección de servicios -->
    <div class="bg-white py-16">
      <div class="container mx-auto px-6">
        <h3 class="text-3xl font-bold text-[#071793] mb-12 text-center">Nuestros Servicios</h3>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div class="text-center">
            <div class="w-20 h-20 bg-[#071793] rounded-full flex items-center justify-center mx-auto mb-4">
              <span class="text-3xl">📋</span>
            </div>
            <h4 class="text-xl font-semibold text-[#071793] mb-3">Valuación Gratuita</h4>
            <p class="text-[#4B6382]">Conoce el valor real de tu propiedad con nuestra valuación profesional</p>
          </div>
          
          <div class="text-center">
            <div class="w-20 h-20 bg-[#A68868] rounded-full flex items-center justify-center mx-auto mb-4">
              <span class="text-3xl">📸</span>
            </div>
            <h4 class="text-xl font-semibold text-[#071793] mb-3">Fotografía Profesional</h4>
            <p class="text-[#4B6382]">Fotografías de alta calidad para mostrar tu propiedad de la mejor manera</p>
          </div>
          
          <div class="text-center">
            <div class="w-20 h-20 bg-[#E3C39D] rounded-full flex items-center justify-center mx-auto mb-4">
              <span class="text-3xl">📞</span>
            </div>
            <h4 class="text-xl font-semibold text-[#071793] mb-3">Asesoría Legal</h4>
            <p class="text-[#4B6382]">Te acompañamos en todo el proceso legal de compra o venta</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Página principal de InmobiEasy
</script> 