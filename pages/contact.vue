<template>
  <div class="min-h-screen bg-[#CDD5DB]">
    <!-- Hero Section -->
    <div class="gradient-bg text-white py-20">
      <div class="container mx-auto px-6 text-center">
        <h1 class="text-5xl md:text-6xl font-bold mb-6">
          <span class="text-[#E3C39D]">Contáctanos</span>
        </h1>
        <p class="text-xl md:text-2xl text-[#A4B5CA] max-w-3xl mx-auto">
          Estamos aquí para ayudarte a encontrar tu hogar ideal. 
          ¡Hablemos sobre tus necesidades inmobiliarias!
        </p>
      </div>
    </div>

    <!-- Información de contacto y formulario -->
    <div class="container mx-auto px-6 py-16">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
        <!-- Información de contacto -->
        <div>
          <h2 class="text-3xl font-bold text-[#071793] mb-8">Información de Contacto</h2>
          
          <div class="space-y-6">
            <div class="card p-6">
              <div class="flex items-center space-x-4">
                <div class="w-12 h-12 bg-[#071793] rounded-full flex items-center justify-center">
                  <span class="text-white text-xl">📍</span>
                </div>
                <div>
                  <h3 class="text-lg font-semibold text-[#071793]">Oficina Principal</h3>
                  <p class="text-[#4B6382]">Nueva Guadalupe, San Miguel</p>
                  <p class="text-[#4B6382]">San Miguel, C987</p>
                </div>
              </div>
            </div>

            <div class="card p-6">
              <div class="flex items-center space-x-4">
                <div class="w-12 h-12 bg-[#A68868] rounded-full flex items-center justify-center">
                  <span class="text-white text-xl">📞</span>
                </div>
                <div>
                  <h3 class="text-lg font-semibold text-[#071793]">Teléfono</h3>
                  <p class="text-[#4B6382]">+503 7586-6244</p>
                  <p class="text-[#4B6382]">Lun - Vie: 9:00 AM - 6:00 PM</p>
                </div>
              </div>
            </div>

            <div class="card p-6">
              <div class="flex items-center space-x-4">
                <div class="w-12 h-12 bg-[#E3C39D] rounded-full flex items-center justify-center">
                  <span class="text-white text-xl">✉️</span>
                </div>
                <div>
                  <h3 class="text-lg font-semibold text-[#071793]">Email</h3>
                  <p class="text-[#4B6382]">info@inmobieasy.com</p>
                  <p class="text-[#4B6382]">ventas@inmobieasy.com</p>
                </div>
              </div>
            </div>

            <div class="card p-6">
              <div class="flex items-center space-x-4">
                <div class="w-12 h-12 bg-[#4B6382] rounded-full flex items-center justify-center">
                  <span class="text-white text-xl">💬</span>
                </div>
                <div>
                  <h3 class="text-lg font-semibold text-[#071793]">WhatsApp</h3>
                  <p class="text-[#4B6382]">+503 7586-6244</p>
                  <p class="text-[#4B6382]">Respuesta en menos de 1 hora</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Redes sociales -->
          <div class="mt-8">
            <h3 class="text-xl font-semibold text-[#071793] mb-4">Síguenos</h3>
            <div class="flex space-x-4">
              <a href="#" class="w-12 h-12 bg-[#071793] rounded-full flex items-center justify-center hover:bg-[#4B6382] transition-colors duration-300">
                <span class="text-white text-xl">📘</span>
              </a>
              <a href="#" class="w-12 h-12 bg-[#A68868] rounded-full flex items-center justify-center hover:bg-[#E3C39D] transition-colors duration-300">
                <span class="text-white text-xl">📷</span>
              </a>
              <a href="#" class="w-12 h-12 bg-[#4B6382] rounded-full flex items-center justify-center hover:bg-[#A4B5CA] transition-colors duration-300">
                <span class="text-white text-xl">🐦</span>
              </a>
              <a href="#" class="w-12 h-12 bg-[#E3C39D] rounded-full flex items-center justify-center hover:bg-[#A68868] transition-colors duration-300">
                <span class="text-white text-xl">💼</span>
              </a>
            </div>
          </div>
        </div>

        <!-- Formulario de contacto -->
        <div class="card p-8">
          <h2 class="text-3xl font-bold text-[#071793] mb-6">Envíanos un Mensaje</h2>
          
          <form @submit.prevent="submitForm" class="space-y-6">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div>
                <label class="block text-[#4B6382] font-medium mb-2">Nombre *</label>
                <input 
                  v-model="form.nombre"
                  type="text" 
                  required
                  class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
                  placeholder="Tu nombre completo"
                >
              </div>
              
              <div>
                <label class="block text-[#4B6382] font-medium mb-2">Apellido *</label>
                <input 
                  v-model="form.apellido"
                  type="text" 
                  required
                  class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
                  placeholder="Tu apellido"
                >
              </div>
            </div>

            <div>
              <label class="block text-[#4B6382] font-medium mb-2">Email *</label>
              <input 
                v-model="form.email"
                type="email" 
                required
                class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
                placeholder="tu@email.com"
              >
            </div>

            <div>
              <label class="block text-[#4B6382] font-medium mb-2">Teléfono</label>
              <input 
                v-model="form.telefono"
                type="tel" 
                class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
                placeholder="+503 7586-6244"
              >
            </div>

            <div>
              <label class="block text-[#4B6382] font-medium mb-2">Tipo de Consulta *</label>
              <select 
                v-model="form.tipoConsulta"
                required
                class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
              >
                <option value="">Selecciona una opción</option>
                <option value="compra">Comprar Propiedad</option>
                <option value="venta">Vender Propiedad</option>
                <option value="renta">Rentar Propiedad</option>
                <option value="valuacion">Valuación Gratuita</option>
                <option value="otro">Otro</option>
              </select>
            </div>

            <div>
              <label class="block text-[#4B6382] font-medium mb-2">Mensaje *</label>
              <textarea 
                v-model="form.mensaje"
                rows="4" 
                required
                class="w-full p-3 border border-[#A4B5CA] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#071793]"
                placeholder="Cuéntanos sobre tus necesidades inmobiliarias..."
              ></textarea>
            </div>

            <div class="flex items-center space-x-2">
              <input 
                type="checkbox" 
                id="newsletter"
                v-model="form.newsletter"
                class="w-4 h-4 text-[#071793] border-[#A4B5CA] rounded focus:ring-[#071793]"
              >
              <label for="newsletter" class="text-[#4B6382] text-sm">
                Suscribirme al newsletter para recibir ofertas especiales
              </label>
            </div>

            <button 
              type="submit" 
              class="btn-primary w-full py-3 rounded-lg font-semibold text-lg"
              :disabled="isSubmitting"
            >
              {{ isSubmitting ? 'Enviando...' : 'Enviar Mensaje' }}
            </button>
          </form>
        </div>
      </div>
    </div>

    <!-- Mapa -->
    <div class="w-full max-w-3xl mx-auto rounded-lg overflow-hidden aspect-video">
  <iframe
    class="w-full h-full"
    src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d7758.112711901948!2d-88.35033!3d13.532133!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8f7b32ce8011f141%3A0x69a3d51d9770508b!2sParque%20de%20Nueva%20Guadalupe!5e0!3m2!1ses-419!2ssv!4v1752105489465!5m2!1ses-419!2ssv"
    style="border:0;"
    allowfullscreen=""
    loading="lazy"
    referrerpolicy="no-referrer-when-downgrade">
  </iframe>
</div>

  </div>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({
  nombre: '',
  apellido: '',
  email: '',
  telefono: '',
  tipoConsulta: '',
  mensaje: '',
  newsletter: false
})

const isSubmitting = ref(false)

const submitForm = async () => {
  isSubmitting.value = true
  
  // Simular envío del formulario
  await new Promise(resolve => setTimeout(resolve, 2000))
  
  // Aquí iría la lógica real para enviar el formulario
  console.log('Formulario enviado:', form.value)
  
  // Resetear formulario
  form.value = {
    nombre: '',
    apellido: '',
    email: '',
    telefono: '',
    tipoConsulta: '',
    mensaje: '',
    newsletter: false
  }
  
  isSubmitting.value = false
  
  // Mostrar mensaje de éxito (aquí podrías usar un toast o alert)
  alert('¡Mensaje enviado con éxito! Nos pondremos en contacto contigo pronto.')
}
</script> 