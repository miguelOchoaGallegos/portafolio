<template>
<section class="hide-overflow">
  <a name="me" />
  <v-layout wrap flat>
      <v-flex
        xs12 
        sm12
        md12
        wrap  
        pa-2            
      >    
      <baseTitle :valueString='profile.nombre' />      
      <baseText :valueString='profile.resumen' />
      <baseTalento />
      <baseTitle :valueString='profile.habilidades' />
      <skill />
      </v-flex>       
  </v-layout>
</section>
</template>  
<script>
export default {
data: () => ({
    profile : {
      nombre:'Miguel Ochoa Gallegos',
      resumen : 'Ingeniero de Sistemas de profesión, experiencia en desarrollo de software, desde soluciones escritorio, hasta aplicaciones web, entusiasta de usar cloud computing y devops para agilizar las tareas de desarrollo !!',
      habilidades: 'Habilidades'

    }    
  }),
components: {  
    baseTitle: () => import('@/components/base/Title'),
    baseText: () => import('@/components/base/Text'),
    baseTalento: () => import('@/components/base/Talento'),
    skill: () => import('@/components/Skill')
    }
}
</script>

