<script setup>
import { ref } from 'vue'
import { PlusIcon, HomeIcon, Bars4Icon } from '@heroicons/vue/24/outline'

const isCollapsed = ref(false)

const toggleMenu = () => {
  isCollapsed.value = !isCollapsed.value
}
</script>

<template>
  <div class="flex">
    <!-- Barra lateral -->
    <aside :class="{'w-80': !isCollapsed, 'w-20': isCollapsed, 'h-screen': true, 'bg-gray-800': true, 'text-white': true, 'rounded-xl': isCollapsed}">
      <!-- Encabezado de la barra lateral -->
      <div class="flex items-center px-5 py-4 border-b border-gray-600">
        <button @click="toggleMenu" :class="{'mx-auto': isCollapsed, 'mr-auto': !isCollapsed}">
          <Bars4Icon class="h-6 w-6"/>
        </button>
        <h2 class="text-xl font-semibold flex-1 text-center" v-if="!isCollapsed">Mi Dashboard</h2>
        <PlusIcon class="h-6 w-6" v-if="!isCollapsed"/>
      </div>

      <!-- Navegación -->
      <nav class="mt-5">
        <ul>
          <li>
            <a href="#" :class="{'justify-center': isCollapsed, 'flex': true, 'items-center': true, 'px-5': true, 'py-3': true, 'hover:bg-gray-700': true}">
              <HomeIcon class="h-6 w-6"/>
              <span class="ml-4" v-if="!isCollapsed">Inicio</span>
            </a>
          </li>
          <!-- Agrega más elementos de navegación según sea necesario -->
        </ul>
      </nav>
    </aside>

    <!-- Contenido principal -->
    <div class="flex-1 p-5">
      Contenido principal...
    </div>
  </div>
</template>

<style scoped>
/* Aquí puedes agregar estilos adicionales si lo necesitas */
</style>
