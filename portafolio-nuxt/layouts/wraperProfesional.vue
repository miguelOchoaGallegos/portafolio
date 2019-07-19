<template>
    <v-app>    
        <Navbar />          
        <v-img :src="require('@/assets/bg.jpg')" class="intro bg-image" />
    <v-content class="pa-0">
      <v-container class="pa-0">
        <nuxt />
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
export default {
    components: {
        Navbar: () => import('@/components/Navbar'),
        contact: () => import('@/pages/contact')
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
</style>
