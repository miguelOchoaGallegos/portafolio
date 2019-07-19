<template>  
  <section    
    class="hide-overflow wrapper-shadow"    
  >  
  <a name="work" />
    <v-layout row wrap white>
      <v-flex
        v-for="(work, i) in works"
            :key="i"
            xs12
            md4                
            mb-12
            pa-2
      >      
      <v-card>        
        <v-card-title primary-title class="justify-center">
            <v-flex text-xs-center xs12 md12>
            <v-img
                :src="require(`@/assets/works/${work.url}`)"
                max-height="200"
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