<template>
  <div class="min-h-screen bg-[#CDD5DB]">
    <!-- Hero Section -->
    <div class="gradient-bg text-white py-16">
      <div class="container mx-auto px-6 text-center">
        <h1 class="text-4xl md:text-5xl font-bold mb-4">
          <span class="text-[#E3C39D]">Propiedades</span> Disponibles
        </h1>
        <p class="text-xl text-[#A4B5CA] max-w-2xl mx-auto">
          Explora nuestra amplia selección de propiedades en venta y renta. 
          Encuentra tu hogar ideal con nuestros filtros avanzados.
        </p>
      </div>
    </div>

    <!-- Filtros avanzados -->
    <div class="bg-white shadow-lg py-8">
      <div class="container mx-auto px-6">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
          <!-- Tipo de operación -->
          <div>
            <label class="block text-[#4B6382] font-medium mb-2">Operación</label>
            <select 
              v-model="filtros.operacion"
              class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
            >
              <option value="">Todas</option>
              <option value="venta">Venta</option>
              <option value="renta">Renta</option>
            </select>
          </div>

          <!-- Tipo de propiedad -->
          <div>
            <label class="block text-[#4B6382] font-medium mb-2">Tipo</label>
            <select 
              v-model="filtros.tipo"
              class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
            >
              <option value="">Todos</option>
              <option value="casa">Casa</option>
              <option value="departamento">Departamento</option>
              <option value="oficina">Oficina</option>
              <option value="terreno">Terreno</option>
            </select>
          </div>

          <!-- Rango de precio -->
          <div>
            <label class="block text-[#4B6382] font-medium mb-2">Precio Máximo</label>
            <select 
              v-model="filtros.precioMax"
              class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
            >
              <option value="">Sin límite</option>
              <option value="500000">$500,000</option>
              <option value="1000000">$1,000,000</option>
              <option value="2000000">$2,000,000</option>
              <option value="5000000">$5,000,000</option>
              <option value="10000000">$10,000,000</option>
            </select>
          </div>

          <!-- Ubicación -->
          <div>
            <label class="block text-[#4B6382] font-medium mb-2">Ubicación</label>
            <input 
              v-model="filtros.ubicacion"
              type="text" 
              placeholder="Ciudad, colonia..."
              class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
            >
          </div>
        </div>

        <!-- Filtros adicionales -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mt-4">
          <div>
            <label class="block text-[#4B6382] font-medium mb-2">Recámaras</label>
            <select 
              v-model="filtros.recamaras"
              class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
            >
              <option value="">Cualquiera</option>
              <option value="1">1+</option>
              <option value="2">2+</option>
              <option value="3">3+</option>
              <option value="4">4+</option>
            </select>
          </div>

          <div>
            <label class="block text-[#4B6382] font-medium mb-2">Baños</label>
            <select 
              v-model="filtros.banos"
              class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
            >
              <option value="">Cualquiera</option>
              <option value="1">1+</option>
              <option value="2">2+</option>
              <option value="3">3+</option>
              <option value="4">4+</option>
            </select>
          </div>

          <div class="flex items-end">
            <button 
              @click="aplicarFiltros"
              class="btn-primary w-full py-3 rounded-lg font-semibold"
            >
              🔍 Aplicar Filtros
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Resultados y ordenamiento -->
    <div class="container mx-auto px-6 py-8">
      <div class="flex flex-col md:flex-row justify-between items-center mb-8">
        <div class="text-[#4B6382] mb-4 md:mb-0">
          Mostrando {{ propiedadesFiltradas.length }} de {{ propiedades.length }} propiedades
        </div>
        
        <div class="flex items-center space-x-4">
          <label class="text-[#4B6382] font-medium">Ordenar por:</label>
          <select 
            v-model="ordenamiento"
            @change="ordenarPropiedades"
            class="p-2 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
          >
            <option value="relevancia">Relevancia</option>
            <option value="precio-asc">Precio: Menor a Mayor</option>
            <option value="precio-desc">Precio: Mayor a Menor</option>
            <option value="fecha">Más Recientes</option>
          </select>
        </div>
      </div>

      <!-- Grid de propiedades -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="propiedad in propiedadesFiltradas" 
          :key="propiedad.id"
          class="card overflow-hidden hover:shadow-xl transition-all duration-300"
        >
          <!-- Imagen de la propiedad -->
          <div class="h-48 bg-gradient-to-br from-[#A4B5CA] to-[#4B6382] flex items-center justify-center relative">
            <span class="text-6xl">{{ propiedad.emoji }}</span>
            <div class="absolute top-4 left-4">
              <span 
                :class="propiedad.operacion === 'venta' ? 'bg-[#E3C39D] text-[#071793]' : 'bg-[#A4B5CA] text-[#071793]'"
                class="px-3 py-1 rounded-full text-sm font-medium"
              >
                {{ propiedad.operacion === 'venta' ? 'Venta' : 'Renta' }}
              </span>
            </div>
            <div class="absolute top-4 right-4">
              <button 
                @click="toggleFavorito(propiedad.id)"
                class="w-8 h-8 bg-white rounded-full flex items-center justify-center hover:bg-[#CDD5DB] transition-colors"
              >
                <span :class="propiedad.favorito ? 'text-red-500' : 'text-gray-400'">❤️</span>
              </button>
            </div>
          </div>

          <!-- Información de la propiedad -->
          <div class="p-6">
            <h3 class="text-xl font-semibold text-[#071793] mb-2">{{ propiedad.titulo }}</h3>
            <p class="text-[#4B6382] mb-3">{{ propiedad.ubicacion }}</p>
            
            <!-- Características -->
            <div class="flex items-center space-x-4 mb-4 text-[#4B6382]">
              <span class="flex items-center">
                <span class="mr-1">🛏️</span>
                {{ propiedad.recamaras }}
              </span>
              <span class="flex items-center">
                <span class="mr-1">🚿</span>
                {{ propiedad.banos }}
              </span>
              <span class="flex items-center">
                <span class="mr-1">📏</span>
                {{ propiedad.metros }}m²
              </span>
            </div>

            <!-- Descripción -->
            <p class="text-[#4B6382] text-sm mb-4">{{ propiedad.descripcion }}</p>

            <!-- Precio y botón -->
            <div class="flex justify-between items-center">
              <div>
                <span class="text-2xl font-bold text-[#A68868]">
                  {{ propiedad.operacion === 'venta' ? '$' + propiedad.precio.toLocaleString() : '$' + propiedad.precio.toLocaleString() + '/mes' }}
                </span>
              </div>
              <button class="btn-primary px-4 py-2 rounded-lg text-sm">
                Ver Detalles
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Paginación -->
      <div class="flex justify-center mt-12">
        <div class="flex space-x-2">
          <button 
            @click="paginaAnterior"
            :disabled="paginaActual === 1"
            class="px-4 py-2 border border-[#A4B5CA] rounded-lg text-[#4B6382] hover:bg-[#A4B5CA] disabled:opacity-50 disabled:cursor-not-allowed"
          >
            Anterior
          </button>
          
          <button 
            v-for="pagina in paginasVisibles" 
            :key="pagina"
            @click="irAPagina(pagina)"
            :class="pagina === paginaActual ? 'bg-[#071793] text-white' : 'border border-[#A4B5CA] text-[#4B6382] hover:bg-[#A4B5CA]'"
            class="px-4 py-2 rounded-lg"
          >
            {{ pagina }}
          </button>
          
          <button 
            @click="paginaSiguiente"
            :disabled="paginaActual === totalPaginas"
            class="px-4 py-2 border border-[#A4B5CA] rounded-lg text-[#4B6382] hover:bg-[#A4B5CA] disabled:opacity-50 disabled:cursor-not-allowed"
          >
            Siguiente
          </button>
        </div>
      </div>
    </div>

    <!-- CTA -->
    <div class="gradient-accent py-16">
      <div class="container mx-auto px-6 text-center">
        <h2 class="text-3xl font-bold text-white mb-6">
          ¿No encuentras lo que buscas?
        </h2>
        <p class="text-white text-xl mb-8 max-w-2xl mx-auto">
          Nuestros agentes están listos para ayudarte a encontrar la propiedad perfecta. 
          ¡Contáctanos y te ayudaremos personalmente!
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <button class="bg-white text-[#071793] px-8 py-3 rounded-lg font-semibold hover:bg-[#CDD5DB] transition-colors duration-300">
            📞 Contactar Agente
          </button>
          <button class="border-2 border-white text-white px-8 py-3 rounded-lg font-semibold hover:bg-white hover:text-[#071793] transition-colors duration-300">
            📋 Solicitar Valuación
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

// Estado de filtros
const filtros = ref({
  operacion: '',
  tipo: '',
  precioMax: '',
  ubicacion: '',
  recamaras: '',
  banos: ''
})

// Estado de ordenamiento
const ordenamiento = ref('relevancia')

// Estado de paginación
const paginaActual = ref(1)
const propiedadesPorPagina = 9

// Datos de propiedades (simulados)
const propiedades = ref([
  {
    id: 1,
    titulo: 'Casa Moderna en Polanco',
    ubicacion: 'Puerto El Triunfo',
    precio: 350000,
    operacion: 'venta',
    tipo: 'casa',
    recamaras: 3,
    banos: 2,
    metros: 180,
    descripcion: 'Hermosa casa de 3 recámaras, 2 baños, cocina equipada y jardín privado.',
    emoji: '🏠',
    favorito: false
  },
  {
    id: 2,
    titulo: 'Departamento de Lujo en Condesa',
    ubicacion: 'San Benito / San Salvador',
    precio: 25000,
    operacion: 'renta',
    tipo: 'departamento',
    recamaras: 2,
    banos: 2,
    metros: 120,
    descripcion: 'Departamento de lujo con vista panorámica, amenidades premium y seguridad 24/7.',
    emoji: '🏢',
    favorito: true
  },
  {
    id: 3,
    titulo: 'Casa Familiar en Lomas',
    ubicacion: 'Lomas Lindas / Sonsonate',
    precio: 4200000,
    operacion: 'venta',
    tipo: 'casa',
    recamaras: 4,
    banos: 3,
    metros: 280,
    descripcion: 'Casa familiar de 4 recámaras con amplio jardín, alberca y cochera para 3 autos.',
    emoji: '🏡',
    favorito: false
  },
  {
    id: 4,
    titulo: 'Oficina Ejecutiva en Reforma',
    ubicacion: 'Reforma, Redondel Constitucion',
    precio: 35000,
    operacion: 'renta',
    tipo: 'oficina',
    recamaras: 0,
    banos: 2,
    metros: 150,
    descripcion: 'Oficina ejecutiva con vista al Ángel de la Independencia, ideal para empresas.',
    emoji: '🏢',
    favorito: false
  },
  {
    id: 5,
    titulo: 'Terreno Residencial',
    ubicacion: 'Cerca de Cascadas Mall, San Salvador',
    precio: 1800000,
    operacion: 'venta',
    tipo: 'terreno',
    recamaras: 0,
    banos: 0,
    metros: 500,
    descripcion: 'Terreno de 500m² en zona residencial, ideal para construir tu casa de ensueño.',
    emoji: '🌳',
    favorito: false
  },
  {
    id: 6,
    titulo: 'Loft Industrial en Roma',
    ubicacion: 'Roma Norte, Sivar',
    precio: 18000,
    operacion: 'renta',
    tipo: 'departamento',
    recamaras: 1,
    banos: 1,
    metros: 85,
    descripcion: 'Loft industrial con techos altos, perfecto para artistas y profesionales creativos.',
    emoji: '🏭',
    favorito: true
  },
  {
    id: 7,
    titulo: 'Casa Colonial en La Libertad',
    ubicacion: 'La Libertad',
    precio: 3800000,
    operacion: 'venta',
    tipo: 'casa',
    recamaras: 3,
    banos: 2,
    metros: 200,
    descripcion: 'Casa colonial restaurada con patio central y acabados de época.',
    emoji: '🏛️',
    favorito: false
  },
  {
    id: 8,
    titulo: 'Penthouse en Santa Fe',
    ubicacion: 'Santa Fe, Cuscatlan',
    precio: 85000,
    operacion: 'renta',
    tipo: 'departamento',
    recamaras: 3,
    banos: 3,
    metros: 220,
    descripcion: 'Penthouse de lujo con terraza privada y vista panorámica de la ciudad.',
    emoji: '🏙️',
    favorito: false
  },
  {
    id: 9,
    titulo: 'Casa Contemporánea en Pedregal',
    ubicacion: 'El Pino / San Salvador',
    precio: 5200000,
    operacion: 'venta',
    tipo: 'casa',
    recamaras: 4,
    banos: 4,
    metros: 320,
    descripcion: 'Casa contemporánea con diseño arquitectónico único y jardín zen.',
    emoji: '🏘️',
    favorito: false
  }
])

// Propiedades filtradas
const propiedadesFiltradas = computed(() => {
  let filtradas = propiedades.value

  // Filtrar por operación
  if (filtros.value.operacion) {
    filtradas = filtradas.filter(p => p.operacion === filtros.value.operacion)
  }

  // Filtrar por tipo
  if (filtros.value.tipo) {
    filtradas = filtradas.filter(p => p.tipo === filtros.value.tipo)
  }

  // Filtrar por precio máximo
  if (filtros.value.precioMax) {
    filtradas = filtradas.filter(p => p.precio <= parseInt(filtros.value.precioMax))
  }

  // Filtrar por ubicación
  if (filtros.value.ubicacion) {
    filtradas = filtradas.filter(p => 
      p.ubicacion.toLowerCase().includes(filtros.value.ubicacion.toLowerCase())
    )
  }

  // Filtrar por recámaras
  if (filtros.value.recamaras) {
    filtradas = filtradas.filter(p => p.recamaras >= parseInt(filtros.value.recamaras))
  }

  // Filtrar por baños
  if (filtros.value.banos) {
    filtradas = filtradas.filter(p => p.banos >= parseInt(filtros.value.banos))
  }

  return filtradas
})

// Paginación
const totalPaginas = computed(() => Math.ceil(propiedadesFiltradas.value.length / propiedadesPorPagina))

const paginasVisibles = computed(() => {
  const paginas = []
  const inicio = Math.max(1, paginaActual.value - 2)
  const fin = Math.min(totalPaginas.value, paginaActual.value + 2)
  
  for (let i = inicio; i <= fin; i++) {
    paginas.push(i)
  }
  
  return paginas
})

// Funciones
const aplicarFiltros = () => {
  paginaActual.value = 1
}

const ordenarPropiedades = () => {
  // Aquí implementarías la lógica de ordenamiento
  console.log('Ordenando por:', ordenamiento.value)
}

const toggleFavorito = (id) => {
  const propiedad = propiedades.value.find(p => p.id === id)
  if (propiedad) {
    propiedad.favorito = !propiedad.favorito
  }
}

const irAPagina = (pagina) => {
  paginaActual.value = pagina
}

const paginaAnterior = () => {
  if (paginaActual.value > 1) {
    paginaActual.value--
  }
}

const paginaSiguiente = () => {
  if (paginaActual.value < totalPaginas.value) {
    paginaActual.value++
  }
}
</script> 