<template>
<section class="hide-overflow">
  <a name="me" />
  <v-layout wrap flat class="pa-0">
      <v-flex
        xs12 
        sm12
        md6 
        wrap  
        pa-2            
      >      
      <v-card flat style="background-color: transparent !important">        
        <v-card-title primary-title class="justify-center">
            <v-flex text-xs-center xs9 md9>
             <v-img :src="require('@/assets/work.gif')" />               
             </v-flex>             
            <v-flex text-xs-center xs9 md9>
            <h3 class="tercero--text">Datos Personales</h3>
            </v-flex>            
            <div>
              <p><strong>Nombre: </strong>Miguel Ochoa Gallegos</p>
              <p><strong>Perfil: </strong>developer</p>
              <p><strong>correo: </strong>miguel.ochoa.gallegos@gmail.com</p>
              <p><strong>celular: </strong>941499556</p>
            </div>            
        </v-card-title>
      </v-card>
      </v-flex>
       <v-flex        
          xs12
          sm12
          md6
          wrap    
          pa-2  
      >     
    <h2 class="tercero--text">Acerca de mi</h2>
    <base-text class="mb-12">Ingeniero de Sistemas de profesión, experiencia en desarrollo, desde soluciones con escritorio, hasta aplicaciones web, entusiasta de usar cloud computing y devops para agilizar las tareas de desarrollo !! 
    </base-text>
    <h2 class="tercero--text">Habilidades</h2>
    <v-layout
            v-for="(skill, i) in skills"
            :key="i"            
            wrap            
            pa-2
          >
            <v-flex
              xs12              
              v-text="skill.name"
              tercero--text
            />
            <v-flex
              xs12
              text-xs-right
              v-text="`${skill.value}%`"
            />
            <v-progress-linear
              :value="skill.value"
              color="tercero"
              height="8"
            />
          </v-layout>
      </v-flex>
  </v-layout>
</section>
</template>  
<script>


export default {
    transition: "default",
    data: () => ({
    skills: [      
      {
        name: 'Web Development',
        value: 90
      },
      {
        name: 'Desktop app',
        value: 90
      },      
      {
        name: 'C#',
        value: 50
      },      
      {
        name: 'Java',
        value: 90
      },      
      {
        name: 'Cloud computing',
        value: 40
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
