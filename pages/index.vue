<template>
  <client-only>
  <div class="home">
      <carousel v-bind="options">
        <slide :style="{'background-image':`url(https://images.pexels.com/photos/6348105/pexels-photo-6348105.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940)`}"></slide>
        <slide :style="{'background-image':`url(https://images.pexels.com/photos/7706590/pexels-photo-7706590.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940)`}"></slide>
        <slide :style="{'background-image':`url(https://images.pexels.com/photos/7190881/pexels-photo-7190881.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940)`}"></slide>
        <slide :style="{'background-image':`url(https://images.pexels.com/photos/4391486/pexels-photo-4391486.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940w)`}"></slide>
      </carousel>
    <div id="services" class="types-services py-10">
      <p class="text-3xl md:text-5xl my-10 text-center font-light">Nuestro Servicios</p>
      <div class="flex flex-wrap justify-center gap-7 w-100">
          <CardServiceVue v-for="service in types_services" :key="service.url" :url="service.url" :name="service.name" :path="service.path" :param="service.param"/>
      </div>
    </div>
    <div class="pedidos flex flex-col items-center p-7 my-10">
      <p class="text-3xl md:text-5xl my-10 text-center font-light mb-5">Recibe mas informacion</p>
      <div class="form-send shadow-2xl p-10 rounded-lg flex flex-col border-2 mt-6">
        <p class="text-4xl font-light text-center">Formulario</p>
        <div class="form-group flex mt-5 justify-between items-center">
          <label class="text-xl" for="">Nombre completo:</label>
          <input type="text" class="ml-5 border-2 border-green-500 rounded-md h-10 p-5" placeholder="Nombre">
        </div>
        <div class="form-group flex flex-row mt-5 items-center justify-between ">
          <label class="text-xl" for="">Correo:</label>
          <input type="email" class="ml-5 border-2 border-green-500 rounded-md h-10 p-5" placeholder="Email">
        </div>
        <div class="form-group flex flex-row mt-5 items-center justify-between ">
          <label class="text-xl" for="">Mensage:</label>
          <textarea class="ml-5 border-2 border-green-500 rounded-md p-5" rows="5" placeholder="Email"></textarea>
        </div>
        <div class="mt-8 flex justify-center">
          <button class="w-32 h-10 bg-green-400 text-white rounded-md hover:shadow-lg duration-700">Enviar</button>
        </div>
      </div>
    </div>
  </div>
  </client-only>
</template>

<script>
import CardServiceVue from '~/components/CardService.vue'

export default {
  components:{
    CardServiceVue
  },
  data() {
    return {
      options: {
        toop: true,
        perPage: 1,
        autoplay: true,
        paginationEnabled: false,
        autoplayTimeout: 3000
      },
      types_services: [
        {path:'/servicios',param: 'express',name: 'Servicio Express',url: '/availability.png'},
        {path:'/servicios',param: 'programado',name: 'Servicio Programado',url: '/delivery-truck.svg'},
        {path:'/servicios',param: 'business',name: 'In Business',url: '/express.svg'},
        {path:'/servicios',param: 'trasporte-personal',name: 'Transporte de Personal',url: '/work-in-progress.svg'},
      ]
    }
  },
}
</script>
<style scoped>
.VueCarousel-slide{
  width: 100%;
  height: 520px;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.home{
  display: flex;
  flex-direction: column;
  margin-top: 70px;
  scroll-behavior: smooth;
}

.form-send{
  width: 58%;
}

.form-group{
  width: 100%;
}

input,textarea{
  width: 60%;
}

@media (max-width: 900px) {
  .VueCarousel-slide{
      height: 50vh;
  }

  .form-send{
    width: 100%;
  }

}
</style>