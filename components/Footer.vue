<template>
  <footer class="bg-gray-800 text-white flex flex-col p-10">
    <div class="flex justify-between">
        <ul class="services">
            <p class="text-2xl md:text-3xl mb-5">Nuestros Servicios</p>
            <li type="disc" class="ml-9">
                <a class="link-footer" href="#">Servicio Express</a>
            </li>
            <li type="disc" class="ml-9">
                <a class="link-footer" href="#">Servicio Programado</a>
            </li>
            <li type="disc" class="ml-9">
                <a class="link-footer" href="#">In Business</a>
            </li>
            <li type="disc" class="ml-9">
                <a class="link-footer" href="#">Transporte de Personal</a>
            </li>
        </ul>
        <div>
            Facebook de guco
        </div>
    </div>
    <div class="flex justify-center gap-3 mt-5">
        <a v-for="icon in icons" :key="icon.name" :style="{'background-color': icon.color}" class="btn-social text-white rounded-full" href="#">
            <i :class="icon.name"></i>
        </a>
    </div>
  </footer>
</template>

<script>
export default {
    data() {
        return {
            icons: [
                {name: 'bx bxl-facebook',color: '#3b5998'},
                {name: 'bx bxl-whatsapp',color: '#25D366'},
                {name: 'bx bxl-twitter',color: '#1DA1F2'},
                {name: 'bx bxl-instagram',color: '#405DE6'},
            ]
        }
    },
}
</script>

<style scoped>
.link-footer{
    color: white;
}

.link-footer:hover{
    transition: .5s;
    color: #34D399;
}

ul li{
    color: #34D399;
}

.btn-social{
    height: 35px;
    width: 35px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
}

.btn-social:hover{
    transition: .5s;
    transform: translateY(-3px);
}

@media (max-width: 900px) {
    footer{
        flex-direction: column;
    }
}
</style>