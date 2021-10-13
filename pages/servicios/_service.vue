<template>
  <div class="service p-7 flex flex-col items-center">
    <p class="text-3xl">Nuestro Servicio</p>
    <div class="flex flex-col items-center">
      <SectionServiceVue v-for="(service,index) in services" :key="service.key" :index="index" :name="service.name"/>
    </div>
    <div id="form-ask" class="section py-9 flex justify-center">
      <div class="form-ask bg-green-400 py-9 rounded-xl">
        <p class="text-center text-white text-4xl mb-7 font-thin">Formulario</p>
        <div class="inputs-group">
            <input type="text" class="form-control ml-5 border-2 border-green-500 rounded-md h-10 p-5" placeholder="Num. Documento">
            <input type="text" class="form-control ml-5 border-2 border-green-500 rounded-md h-10 p-5" placeholder="Nombre">
            <input type="tel" class="form-control ml-5 border-2 border-green-500 rounded-md h-10 p-5" placeholder="Celular / Telefono">
            <input type="email" class="form-control ml-5 border-2 border-green-500 rounded-md h-10 p-5" placeholder="Correo">

            <textarea class="form-control ml-5 border-2 border-green-500 rounded-md p-5" rows="5" placeholder="Mensaje"></textarea>
            <button class="bg-white w-32 h-10 rounded-md hover:shadow-lg duration-700 mt-5">Enviar</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SectionServiceVue from '~/components/SectionService.vue'

export default {
  components:{
    SectionServiceVue
  },
  data() {
    return {
      services:[
        {key: 'express',name: 'Servicio Express',url: ''},
        {key: 'programado',name: 'Servicio Programado',url: ''},
        {key: 'business',name: 'In Business',url: ''},
        {key: 'trasporte-personal',name: 'Transporte de Personal',url: ''},
      ]
    }
  },
  created() {
    if(this.$route.params.service){
      this.services = this.services.filter((service)=> service.key === this.$route.params.service);
    }
  },
}
</script>

<style scoped>

.section{
  width: 100%;
}

.service{
  margin-top: 100px;
}

.form-ask{
  width: 50%;
}
.inputs-group{
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.form-control{
    width: 70%;
    margin-top: 10px;
}

@media (max-width: 900px) {
  .form-ask{
    width: 90%;
  }
}
</style>