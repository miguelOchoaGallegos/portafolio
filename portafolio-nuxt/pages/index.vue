<template>
<v-app style="background-color:#fff">  
    
    <v-content>
      <v-container>
          <bannerPage titulo="Acerca de mi " />
          <me />        
      </v-container>
    </v-content>     
    <v-content style="background-color:#f8f9fa!important">
      <v-container>
          <bannerPage titulo="Servicios" />
          <services />        
      </v-container>
    </v-content> 
    
    <v-content>
      <v-container>        
        <bannerPage titulo="Portafolio" />
          <work />
      </v-container>
    </v-content> 
    
    <v-content style="background-color:#f8f9fa!important">
      <v-container>                
        <bannerPage titulo="Contacto" />    
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

