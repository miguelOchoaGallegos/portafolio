<template>
  <section
    id="recent-projects"
    class="hide-overflow"
  >
  <a name="proy" />
    <v-layout>
      <v-flex
        xs12
        md6        
        text-xs-center
        pa-5        
      >
        <base-bubble-1
          style="transform: rotate(180deg) translateX(25%)"
        />
        <base-heading class="primary--text">
          Proyectos recientes
        </base-heading>
        <base-text>
          Proyectos que se encuentran en desarrollo<br>          
        </base-text>
        <v-spacer />
        <v-card>
          <v-container
            grid-list-md
            pa-2
          >
            <v-layout wrap>
              <v-flex
                v-for="project in projects"
                :key="project"
                xs12
                md6
              >
                <a href="#">
                  <v-img
                    :src="require(`@/assets/${project}.jpeg`)"
                    max-height="200"
                  />
                </a>
              </v-flex>
            </v-layout>
          </v-container>
        </v-card>
      </v-flex>
      <v-flex
        hidden-sm-and-down
        md6
      >
        <v-img
          :src="require('@/assets/buildproyects.png')"
          height="100%"
        />
      </v-flex>
    </v-layout>
  </section>
</template>

<script>
export default {    
  data: () => ({
    projects: [
      'project1',
      'project2',
      'project3',
      'friterm'
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
