<template>
<v-app>    
    <me />    
    <bannerPage titulo="Servicios" />
    <services />
    <bannerPage titulo="Portafolio" />
    <work />
    <bannerPage titulo="Contacto" />
    <contact />    
</v-app>
</template>

<script>
export default {
  layout: 'wraperProfesional',
  components: {        
    me: () => import('@/pages/me'),    
    services: () => import('@/pages/services'),    
    work: () => import('@/pages/work'),        
    bannerPage: () => import('@/components/BannerPage'),
    contact: () => import('@/pages/contact') 
  }
}
</script>
<style>

</style>

