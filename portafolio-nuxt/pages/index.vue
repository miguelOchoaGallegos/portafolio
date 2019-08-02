<template>
<v-app style="background-color:#fff">  
    <v-content class="pa-0">
      <v-container class="pa-0">        
        <v-layout row white>
          <me />
        </v-layout>        
      </v-container>
    </v-content> 
    <bannerPage titulo="Servicios" />
    <v-content>
      <v-container>        
          <services />        
      </v-container>
    </v-content> 
    <bannerPage titulo="Portafolio" />
    <v-content>
      <v-container>        
          <work />
      </v-container>
    </v-content> 
    <bannerPage titulo="Contacto" />    
    <v-content>
      <v-container>                
          <contact />        
      </v-container>
    </v-content> 
    
</v-app>
</template>

<script>
export default {
  layout: 'wraperProfesional',
  components: {        
    me: () => import('@/pages/me'),    
    services: () => import('@/pages/services'),    
    work: () => import('@/pages/work'),            
    contact: () => import('@/pages/contact') ,
    bannerPage: () => import('@/components/BannerPage'),
    typer: () => import('@/components/Typer')
  }
}
</script>
<style>

</style>

