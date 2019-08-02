<template>  
  <section    
    class="hide-overflow"    
  >  
  <a name="services" />
    <v-layout wrap flat>       
      <v-flex        
          xs12
          sm12
          md4      
          pa-2
      >      
      <v-card style="background-color: transparent !important">        
        <v-card-title tercero-title class="justify-center">
            <v-flex text-xs-center xs12 md4 pa-2>
            <div class="service-box">
            <span class="ico-circle">
            <v-icon            
              size="52"
              color="tercero"
              >web</v-icon>
            </span>            
             </div>
             </v-flex>             
            <v-flex text-xs-center xs12 md12>
            <h3 class="">Diseño</h3>
            <div>Creación de proyectos desktop y web !.</div>
            </v-flex>
        </v-card-title>
      </v-card>
      </v-flex>
      <v-flex        
          xs12
          sm12
          md4          
          pa-2
      > 
      <v-card style="background-color: transparent !important">        
        <v-card-title tercero-title class="justify-center">
            <v-flex text-xs-center xs12 md4 pa-2>
            <div class="service-box">
            <span class="ico-circle">
            <v-icon            
              size="52"
              color="tercero"
              >code</v-icon>
            </span>            
             </div>
             </v-flex>             
            <v-flex text-xs-center xs12 md12>
            <h3 class="">Desarrollo</h3>
            <div>Usando lenguajes con grandes comunidades.</div>
            </v-flex>
        </v-card-title>
      </v-card>
      </v-flex>
      <v-flex        
          xs12
          sm12
          md4          
          pa-2
      > 
 <v-card style="background-color: transparent !important">        
        <v-card-title tercero-title class="justify-center">
            <v-flex text-xs-center xs12 md4 pa-2>
            <div class="service-box">
            <span class="ico-circle">
            <v-icon            
              size="52"
              color="tercero"
              >contact_support</v-icon>
            </span>            
             </div>
             </v-flex>             
            <v-flex text-xs-center xs12 md12>
            <h3 class="">Soporte</h3>
            <div>Apoyo luego de entregar software.</div>
            </v-flex>
        </v-card-title>
      </v-card>
      </v-flex>
    </v-layout>
  </section>
</template>
<script>
export default {
  transition: "default",
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
    box-shadow: 0 0 0 10px #fb8c00;
    display: block;
}
</style>