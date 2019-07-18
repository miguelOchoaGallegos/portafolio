<template>
  <section
    id="welcome"
    class="hide-overflow"
  >  
    <v-layout>
      <v-flex
        hidden-sm-and-down
        md6
      >
        <v-img
          :src="require('@/assets/welcome.png')"
          height="100vh"
        />
      </v-flex>
      <v-flex
        xs12
        md6
        align-content-space-between
        layout
        :pa-5="$vuetify.breakpoint.smAndDown"
        wrap
      >
        <base-bubble-1
          style="transform: rotate(180deg) translateY(25%)"
        />
        <v-layout
          align-center
          justify-center
        >
          <v-flex
            xs10
            md6
          >
            <base-heading class="primary--text">Bienvenido!</base-heading>
            <base-text>                
                Este espacio esta destinado a publicar los proyectos que estaré desarrollando, si tienes dudas dejaré mis datos de contacto, asi como las fuentes en repo Git.
            </base-text>            
          </v-flex>
        </v-layout>

        <base-bubble-2
          style="transform: rotate(180deg) translate(-200px, -15%)"
        />
      </v-flex>
    </v-layout>
  </section>
</template>
<script>
export default {
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

