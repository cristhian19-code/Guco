<template>
  <div id="sidebar" class="bg-white">
    <ul>
        <li :class="$route.path == '/' ? 'text-green-500' : ''" class="btn-sidebar shadow-sm hover:shadow-lg rounded-md">
            <nuxt-link to="/">
                Inicio
            </nuxt-link>
        </li>
        <li :class="$route.path == '/nosotros' ? 'text-green-500' : ''" class="btn-sidebar shadow-sm hover:shadow-lg rounded-md">
            <nuxt-link to="/nosotros">
                Nosotros
            </nuxt-link>
        </li>
        <li :class="$route.path == '/servicios' ? 'text-green-500' : ''" class="btn-sidebar shadow-sm hover:shadow-lg rounded-md">
            <nuxt-link to="/servicios">
                Servicios
            </nuxt-link>
        </li>
        <li :class="$route.path == '/blog' ? 'text-green-500' : ''" class="btn-sidebar shadow-sm hover:shadow-lg rounded-md">
            <nuxt-link to="/blog">
                Blog
            </nuxt-link>
        </li>
        <li :class="$route.path == '/protocolos' ? 'text-green-500' : ''" class="btn-sidebar shadow-sm hover:shadow-lg rounded-md">
            <nuxt-link to="/protocolos">
                Protocolos
            </nuxt-link>
        </li>
    </ul>

    <div id="sidebar-btn">
        <img class="icon-menu" src="/menu.svg" alt="" height="30">
    </div>
</div>
</template>

<script>
import $ from 'jquery'

export default {
    mounted() {
        $(document).ready(function() {
            $('#sidebar-btn').on('click', function() {
                $('#sidebar').toggleClass('visible');
            });
        });
    },
}
</script>

<style>
#sidebar {
  width: 300px;
  position: fixed;
  height: 100%;
  top: 0;
  z-index: 10000;
  left: -300px;
  transition: left 0.5s ease;
}

#sidebar.visible {
  left: 0px;
  transition: left 0.7s ease;
}

ul {
  margin: 0;
  padding: 0;
}

#sidebar-btn {
  display: inline-block;
  vertical-align: middle;
  width: 20px;
  height: 15px;
  cursor: pointer;
  margin: 20px;
  position: absolute;
  right: -60px;
  top: 0px;
}

.btn-sidebar{
    margin: 20px 0;
    width: 100%;
    height: 40px;
    font-size: 15px;
    font-weight: 500;
    height: 50px;
    text-align: center;
    vertical-align: middle;
}

.btn-sidebar:hover{
    transition: .5s;
}
</style>