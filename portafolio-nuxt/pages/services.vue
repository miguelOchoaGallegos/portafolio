<template>  
  <section
    id="services"
    class="hide-overflow"        
  >  
  <a name="serv" />
    <v-layout>
      <v-flex
        hidden-sm-and-down
        md6
      >
        <v-img
          :src="require('@/assets/services.png')"
          height="100%"
        />
      </v-flex>
      <v-flex
        xs12
        md6
        text-xs-center
        pa-5        
      >
      <v-layout
          align-center
          justify-center
          fill-height
          wrap
        >
        <v-flex xs12>
            <base-bubble-2
              style="transform: translateX(55%)"
            />
            <base-heading class="primary--text">
              Servicios
            </base-heading>  
            <base-text class="mb-5">
              Creación de software desktop/web-responsive a demanda usando tecnologías que tienen una gran comunidad de apoyo.
            </base-text>            
        </v-flex>
        <v-flex
            v-for="(service, i) in services"
            :key="i"
            md6
            text-xs-center
            mb-3
          >
          <v-avatar
              class="elevation-6 mb-2"
              color="#69A1BB"
              size="64"
              tile
            >
              <v-icon
                dark
                size="52"
                v-text="service.icon"
              />
          </v-avatar>
          <no-ssr>
          <base-text>
            <div
                class="mb-2"
                v-text="service.name"
              />
            <div v-html="service.blurb" />
          </base-text>
          </no-ssr>
        </v-flex>
      </v-layout>
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
        blurb: 'Creación de webs responsive.'
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
         baseBtn: () => import('@/components/base/Btn'),
         baseHeading: () => import('@/components/base/Heading'),
         baseSubheading: () => import('@/components/base/Subheading'),
         baseText: () => import('@/components/base/Text'),
         baseBubble1: () => import('@/components/base/Bubble1'),
         baseBubble2: () => import('@/components/base/Bubble2')
    }
}
</script>
