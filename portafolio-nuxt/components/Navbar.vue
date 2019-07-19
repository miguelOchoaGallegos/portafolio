<template>  
    <v-toolbar v-scroll="onScroll" 
    :color="isTransparent ? 'transparent' : 'primary'" app flat>      
    <!--<v-toolbar-side-icon> 
      <img :src="require('@/assets/logo-min.png')" style="height:75px;">
      </v-toolbar-side-icon> -->
    <v-avatar> 
      <img :src ="require('@/assets/logo-min.png')"  /> 
      </v-avatar>
    <v-toolbar-title class="white--text" v-text="titulo" />     
    <v-spacer></v-spacer>
    
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn
        class="white--text"
        v-for="item in menu"
        :key="item.icon"        
        flat
        @click="redirectPage(item.link)"
        >{{ item.title }}        
        <v-icon class="secondary--text">{{item.icon}}</v-icon>
        </v-btn>
    </v-toolbar-items>
    <v-menu class="hidden-md-and-up">
        <v-toolbar-side-icon slot="activator"></v-toolbar-side-icon>
        <v-list>
        <v-list-tile v-for="item in menu" :key="item.icon">
        <v-list-tile-content>            
            <v-list-tile-title>
                <a :href="item.link" style="text-decoration:none;" class="primary--text">
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
    titulo : 'Portafolio miguelo',
    menu: [
       { icon: 'home', title: 'inicio' , link :'/' },
        { icon: 'account_box', title: 'acerca de mi' , link:'#me' },
        { icon: 'start', title: 'servicios' , link:'#services' },
        { icon: 'code', title: 'trabajos' , link:'#work' },
        { icon: 'contact_mail', title: 'contacto' , link:'#contact' }
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
