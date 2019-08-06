<template>  
  <section    
    class="hide-overflow"    
  >  
  <a name="services" />
   <v-layout wrap flat>
     <v-flex md12 xs12 sm12>
     <baseText :valueString='content' />
     </v-flex>
      <v-flex        
        v-for="(service, i) in services"
        :key="i"
        xs12 
        sm4
        md4
        wrap  
        pa-4
      >      
      <cardCustom 
      v-bind:title="service.name" 
      v-bind:message="service.blurb"       
      v-bind:icon="service.icon"
      />
      </v-flex>
    </v-layout>
  </section>
</template>
<script>
export default {
  transition: "default",
  data: () => ({
    content : 'Considerando los años de experiencia en el rubro de T.I son:',
    services: [
      {
        name: 'Diseño',
        icon: 'web',
        blurb: 'Creación de proyectos desktop y web !.'
      },
      {
        name: 'Response design',
        icon: 'tablet_android',
        blurb: 'diseño adaptado a tablets y moviles.'
      },
      {
        name: 'Desarrollo',
        icon: 'code',
        blurb: 'Usando lenguajes con grandes comunidades.'
      },
      {
        name: 'Soporte',
        icon: 'contact_support',
        blurb: 'Apoyo luego de entregar software.'
      }      
    ]
  }),
  components: {
    cardCustom: () => import('@/components/CardCustom'),
    baseText: () => import('@/components/base/Text')
  }
}
</script>
