<template>  
  <section    
    class="hide-overflow wrapper-shadow"    
  >  
  <a name="services" />
    <v-layout row wrap white>
      <v-flex
        v-for="(service, i) in services"
            :key="i"
            xs12
            md4                
            mb-12
            pa-2
      >      
      <v-card>        
        <v-card-title primary-title class="justify-center">
            <v-flex text-xs-center xs12 md12 pa-2>
            <div class="service-box">
            <span class="ico-circle ">
            <v-icon            
              size="52"
              color="primary"
              v-text="service.icon" />
            </span>            
             </div>
             </v-flex>             
            <v-flex text-xs-center xs12 md6>
            <h3 class="">{{service.name}}</h3>
            <div>{{service.blurb}}</div>
            </v-flex>
        </v-card-title>        
        
      </v-card>
      </v-flex>
    </v-layout>
  </section>
</template>
<script>
export default {
  data: () => ({
    services: [
      {
        name: 'Diseño',
        icon: 'web',
        blurb: 'Creación de proyectos desktop y web !.'
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
         baseHeading: () => import('@/components/base/Heading'),
         baseSubheading: () => import('@/components/base/Subheading'),
         baseText: () => import('@/components/base/Text')
    }
}
</script>
<style>
.wrapper-shadow{
    box-shadow: 0 1px 1px 0 rgba(0, 0, 0, 0.06), 0 2px 5px 0 rgba(0, 0, 0, 0.2);
}
.service-box .ico-circle {
  transition: all 500ms ease;
  font-size: 4rem;
}
.ico-circle {
    height: 100px;
    width: 100px;
    font-size: 2rem;
    border-radius: 50%;
    line-height: 1.55;
    margin: 0 auto;
    text-align: center;
    box-shadow: 0 0 0 10px #1976d2;
    display: block;
}
</style>