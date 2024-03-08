<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faUser, faLock, faEye, faEyeSlash } from '@fortawesome/free-solid-svg-icons';

const passwordShown = ref(false);
const router = useRouter();

const togglePasswordVisibility = () => {
  passwordShown.value = !passwordShown.value;
};

const navigateToDashboard = () => {
  router.push({ name: 'AdminDashboard' });
};
</script>

<template>
  <div class="flex justify-center items-center h-screen bg-white">
    <div class="w-full max-w-sm">
      <form @submit.prevent="navigateToDashboard" class="bg-gray-50 shadow-xl rounded-2xl px-10 pt-8 pb-8 mb-8">
        <h1 class="text-center text-4xl font-bold text-pink-600 mb-12">EduPago</h1>
        <h2 class="text-center text-2xl font-extrabold text-gray-900 mb-10">Iniciar sesión</h2>
        <div class="mb-6 relative">
          <FontAwesomeIcon :icon="faUser" class="absolute text-gray-400 left-3 top-4" />
          <input class="pl-10 shadow appearance-none border border-gray-300 rounded-lg w-full py-3 px-3 text-gray-700 leading-tight focus:ring-blue-500 focus:border-blue-500" id="username" type="text" placeholder="Usuario">
        </div>
        <div class="mb-6 relative">
          <FontAwesomeIcon :icon="faLock" class="absolute text-gray-400 left-3 top-4" />
          <input :type="passwordShown ? 'text' : 'password'" class="pl-10 shadow appearance-none border border-gray-300 rounded-lg w-full py-3 px-3 text-gray-700 leading-tight focus:ring-blue-500 focus:border-blue-500" id="password" placeholder="Contraseña">
          <FontAwesomeIcon :icon="passwordShown ? faEyeSlash : faEye" @click="togglePasswordVisibility" class="absolute text-gray-400 right-3 top-4 cursor-pointer" />
        </div>
        <div class="flex items-center justify-between mb-12">
          <a class="inline-block align-baseline font-bold text-sm text-blue-600 hover:text-blue-800" href="#">
            ¿Olvidaste tu contraseña?
          </a>
        </div>
        <div class="flex items-center justify-center">
          <button class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-4 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-opacity-50" type="submit">
            Iniciar sesión
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped>
/* Aquí tus estilos específicos si los necesitas */
</style>
