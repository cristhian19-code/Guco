<template>
    <div class="default-layout flex-col">
        <SidebarVue v-if="windowWidth<900"/>
        <NavbarVue/>
        <Nuxt/>
        
        <FooterVue/>
    </div>
</template>

<script>
import { provide, ref } from '@vue/composition-api'
import FooterVue from '~/components/Footer.vue'
import NavbarVue from '~/components/Navbar.vue'
import SidebarVue from '~/components/Sidebar.vue'

export default {
    components: {
        NavbarVue,
        FooterVue,
        SidebarVue
    },
    setup() {
        const windowWidth = ref(900);
        provide('windowWidth',windowWidth);

        return{
            windowWidth
        }
    },
    mounted() {
        window.onresize = () => {
            this.windowWidth = window.innerWidth
        }
        
    },
}
</script>