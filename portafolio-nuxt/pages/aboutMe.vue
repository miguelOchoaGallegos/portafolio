<template>
  <section
    id="about"
    class="hide-overflow"
  >
  <a name="about" />
    <v-layout white>
      <v-flex
        xs12
        md6
        pa-5
      >
        <base-bubble-1
          style="transform: translate(5%, -5%)"
        />
        <base-heading class="primary--text">
          Acerca de mi
        </base-heading>

        <base-text class="mb-5">
          Ingeniero de Sistemas de profesión <br>
          Experiencia en desarrollo, desde soluciones con escritorio, hasta aplicaciones web<br>
          Entusiasta de usar cloud computing y devops para agilizar las tareas de desarrollo !! 
        </base-text>
        <base-subheading class="primary--text">
          Habilidades
        </base-subheading>
        <base-text class="mb-5">
          Las habilidades destacadas en el mundo de TI,<br>
          son las que se muestran a continuaci&oacute;n
        </base-text>        
        <v-alert
          outlined
          color="light"
          style="display:block"
        >
          <v-layout
            v-for="(skill, i) in skills"
            :key="i"
            style="color: #69A1BB;"
            wrap
          >
            <v-flex
              xs6              
              v-text="skill.name"
            />
            <v-flex
              xs6
              text-xs-right
              v-text="`${skill.value}%`"
            />
            <v-progress-linear
              :value="skill.value"
              color="primary"
              height="8"
            />
          </v-layout>
        </v-alert>
      </v-flex>
      <v-flex
        hidden-sm-and-down
        md6
      >
        <v-img
          :src="require('@/assets/aboutme.png')"
          height="100%"
        />
      </v-flex>
    </v-layout>
  </section>
</template>

<script>
export default {
  data: () => ({
    skills: [
      {
        name: 'Web Design',
        value: 60
      },
      {
        name: 'Web Development',
        value: 80
      },
      {
        name: 'Desktop app',
        value: 90
      },
      {
        name: 'Java',
        value: 90
      },
      {
        name: 'C#',
        value: 60
      },
      {
        name: 'Cloud computing',
        value: 40
      }
    ]
  }),
  components: {
         baseBtn: () => import('@/components/base/Btn'),
         baseHeading: () => import('@/components/base/Heading'),
         baseSubheading: () => import('@/components/base/Subheading'),
         baseText: () => import('@/components/base/Text'),
         baseBubble1: () => import('@/components/base/Bubble1'),
         baseBubble2: () => import('@/components/base/Bubble2')
    }
}
</script>
