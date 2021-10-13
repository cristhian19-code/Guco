<template>
  <div :class="windowWidth >= 900 ?'justify-between':'justify-center'" class="navbar h-20 flex items-center shadow bg-white">
    <div class="icon-page">
      <nuxt-link to="/">
        <img src="https://gucoby.com/wp-content/uploads/2021/05/cropped-logo-GUCO-1.png" alt="" height="60" width="60">
      </nuxt-link>
    </div>
    <div v-if="windowWidth >= 900" class="buttons-link flex justify-around gap-4">
      <nuxt-link to="/">
        <button :class="$route.path == '/' ? 'text-green-500' : ''" class="btn-navbar bg-white rounded-md shadow-lg">Inicio</button>
      </nuxt-link>
      <nuxt-link to="/servicios">
        <button :class="$route.path == '/servicios' ? 'text-green-500' : ''" class="btn-navbar bg-white rounded-md shadow-lg">Servicios</button>
      </nuxt-link>
      <nuxt-link to="/nosotros">
        <button :class="$route.path == '/nosotros' ? 'text-green-500' : ''" class="btn-navbar bg-white rounded-md shadow-lg">Nosotros</button>
      </nuxt-link>
      <nuxt-link to="/blog">
        <button :class="$route.path == '/blog' ? 'text-green-500' : ''" class="btn-navbar bg-white rounded-md shadow-lg">Blog</button>
      </nuxt-link>
      <nuxt-link to="/protocolos">
        <button :class="$route.path == '/protocolos' ? 'text-green-500' : ''" class="btn-navbar bg-white rounded-md shadow-lg">Protocolos</button>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
import { inject } from '@vue/composition-api'
export default {
  setup() {
    const windowWidth = inject('windowWidth');

    return {
      windowWidth
    }
  }
}
</script>

<style scoped>
.navbar{
  padding: 0 20px;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
}

.btn-navbar{
  width: 125px;
  height: 40px;
  font-size: 15px;
  font-weight: 500;
}

.btn-navbar:hover{
  transition: .5s;
  box-shadow: none;
  color: #9CA3AF;
}
</style>