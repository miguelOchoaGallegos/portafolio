<template>
    <v-app>    
        <Navbar />          
        <v-img :src="require('@/assets/bg.jpg')" class="intro bg-image" />                
    <v-content class="pa-0">
      <v-container class="pa-0">
        <v-layout row class="pa-3">
          <vue-typer
              :text='["Diseño web","Desarrollo web","Piezas gráficas"]'
              :repeat='Infinity'
              :shuffle='false'
              initial-action='typing'
              :pre-type-delay='70'
              :type-delay='70'
              :pre-erase-delay='2000'
              :erase-delay='250'
              erase-style='select-all'
              :erase-on-complete='false'
              caret-animation='blink'              
            ></vue-typer>
        </v-layout>
        <v-layout row wrap white>
          <nuxt />
        </v-layout>
        
      </v-container>
    </v-content>    
    <v-content class="pa-5" />
    <!-- <contact /> -->
    <v-footer app color="primary">
    <v-layout
      justify-center
      row
      wrap      
    >     
      <v-flex
        primary        
        py-0
        text-xs-center
        white--text
        xs12
      >
        &copy;{{ new Date().getFullYear() }} :: <strong> Todos los derechos reservados -  portafolio miguelo</strong>
      </v-flex>
    </v-layout>
  </v-footer>
    </v-app>  
</template>
<script>
import { VueTyper } from 'vue-typer';

export default {
    components: {
        Navbar: () => import('@/components/Navbar'),
        contact: () => import('@/pages/contact'),
        VueTyper
    },
    data : () =>({
        fixed: false,
    })
}
</script>
<style>
/*.theme--light.v-footer {
    background: primary;    
}*/

.bg-image {
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
  background-position: center center;  
}

.intro {
  height: 100vh;
  position: relative;
  color: #fff;
}

.intro .intro-content {
  text-align: center;
  position: absolute;
}

.intro .overlay-itro {
  background-color: rgba(0, 0, 0, 0.6);
  position: absolute;
  top: 0;
  left: 0px;
  padding: 0;
  height: 100%;
  width: 100%;
  opacity: .9;
}

.intro .intro-title {
  color: #fff;
  font-weight: 600;
  font-size: 3rem;
}

.intro .intro-subtitle {
  font-size: 1.5rem;
  font-weight: 300;
}

.intro .text-slider-items {
  display: none;
}

.intro-single {
  height: 350px;
}

.intro-single .intro-content {
  margin-top: 30px;
}

.intro-single .intro-title {
  text-transform: uppercase;
  font-size: 3rem;
}

.intro-single .breadcrumb {
  background-color: transparent;
  color: #1976d2;
}

.intro-single .breadcrumb .breadcrumb-item:before {
  color: #cde1f8;
}

.intro-single .breadcrumb .breadcrumb-item.active {
  color: #cde1f8;
}

.intro-single .breadcrumb a {
  color: #fff;
}

.application{
  font-family: monospace !important;;
}


.vue-typer {
  font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;
  font-size: 25px;
}
.vue-typer .custom.char.typed {
  color: #1976d2;
}
.vue-typer .custom.char.selected {
  color: #ce0d0d;
}

.vue-typer .custom.caret {
  animation: rocking 1s ease-in-out 0s infinite;
}
.vue-typer .custom.caret.typing {
  background-color: #1976d2;
}
.vue-typer .custom.caret.selecting {
  display: inline-block;
  background-color: #ce0d0d;
}
</style>
