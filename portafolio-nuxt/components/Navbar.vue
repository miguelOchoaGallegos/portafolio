<template>    
    <v-toolbar v-scroll="onScroll" 
    :color="isTransparent ? 'transparent' : '#000'" app flat>        
    <!-- <v-avatar> 
      <img :src ="require('@/assets/logo-min.png')"  /> 
      </v-avatar>-->
    <v-toolbar-title :class="isTransparent ? 'white--text' : 'tercero--text'" v-text="titulo" />     
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
    <v-btn        
        v-for="item in menu"
        :key="item.icon"
        flat
        @click="redirectPage(item.link)"
        :class="isTransparent ? 'white--text' : 'tercero--text'"
        >{{ item.title }}        
        </v-btn>
    </v-toolbar-items>
    <v-menu class="hidden-md-and-up">
        <v-toolbar-side-icon class="white--text" slot="activator"></v-toolbar-side-icon>
        <v-list>
        <v-list-tile v-for="item in menu" :key="item.icon">
        <v-list-tile-content>            
            <v-list-tile-title>
                <a :href="item.link" style="text-decoration:none;" class="tercero--text">
                {{ item.title }}
                </a></v-list-tile-title>
        </v-list-tile-content>
        </v-list-tile>   
    </v-list>
    </v-menu>

  </v-toolbar>  
</template>
<style>
.container {
    width: 100%;    
}

</style>
<script>
export default {
  data: () => ({
    isTransparent: true,    
    colorDefault : '#ff0000',
    titulo : 'Portafolio',
    menu: [
       { icon: 'init', title: 'inicio' , link :'#ini' },
        { icon: 'me', title: 'acerca de mi' , link:'#me' },
        { icon: 'ser', title: 'servicios' , link:'#services' },
        { icon: 'tr', title: 'trabajos' , link:'#work' },
        { icon: 'co', title: 'contacto' , link:'#contact' }
    ]
  }),

  methods: {
    onScroll () {
      this.isTransparent = window.pageYOffset < 200
    },
    redirectPage(refName) {
      window.location.href=refName;
    }
  }
}
</script>
