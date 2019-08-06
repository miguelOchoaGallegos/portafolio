<template>  
  <section    
    class="hide-overflow"       
  >  
  <a name="work" />
    <v-layout wrap flat>
      <v-flex md12 xs12 sm12>
        <baseText :valueString='content' />
      </v-flex>
       <v-flex        
        v-for="(work, i) in works"
        :key="i"
        xs12 
        sm12
        md12          
        pa-4        
      > 
      <cardCustomImage
      v-bind:title="work.name" 
      v-bind:message="work.desc"       
      v-bind:path="work.url"
      v-bind:link="work.link"
      />    
      </v-flex>
    </v-layout>
  </section>
</template>
<script>
export default {  
  data: () => ({
    content : 'Los proyectos expuesto fueron realizados desde 2019 bajo modalidad de freelance, cumpliendo con las exigencias y expectativas de los clientes: ',
    works: [
      {
        name: 'Friterm Perú',
        url: 'friterm.jpeg',
        desc: 'Creación de pagina web usando spring boot + thymeleaf.',
        link : 'https://friterm-web.herokuapp.com/home'
      }      
    ]
  }),
  components: {
      cardCustomImage: () => import('@/components/CardCustomImage'),
      baseText: () => import('@/components/base/Text'),
    }
}
</script>
