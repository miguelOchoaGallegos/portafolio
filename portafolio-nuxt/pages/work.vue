<template>  
  <section    
    class="hide-overflow"       
  >  
  <a name="work" />
    <v-layout flat row align-center justify-center>     
      <v-flex
        v-for="(work, i) in works"
            :key="i"
            xs6
            md5           
            pa-5
      >      
      <v-card style="background-color: transparent !important">        
        <v-card-title primary-title class="justify-center">           
            <v-flex xs12 md6 pa-2>
              <v-img
                  :src="require(`@/assets/works/${work.url}`)"                  
                   max-width="300"
                  max-height="300"
                  />                
              </v-flex>
             <v-flex text-xs-center xs12 md6>
                <h3 class="">{{work.name}}</h3>
                <div>{{work.desc}}</div>
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
    works: [
      {
        name: 'Friterm Perú',
        url: 'friterm.jpeg',
        desc: 'Creación de pagina web usando spring boot + thymeleaf.'
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
</style>