<template>
<v-toolbar v-scroll="onScroll"
:color="isTransparent ? 'transparent' : '#F5F5F5'" app flat>
    <v-toolbar-title v-text="titulo" />
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
        <v-btn
        v-for="item in menu"
        :key="item.icon"        
        flat
        @click="redirectPage(item.link)"
        >{{ item.title }}        
        <v-icon color="dark">{{item.icon}}</v-icon>
        </v-btn>
    </v-toolbar-items>
    <v-menu class="hidden-md-and-up">
    <v-toolbar-side-icon slot="activator"></v-toolbar-side-icon>
    <v-list>
        <v-list-tile v-for="item in menu" :key="item.icon">
        <v-list-tile-content>
            <!-- <v-list-tile-title @click="redirectPage(item.link)">{{ item.title }}</v-list-tile-title> -->
            <v-list-tile-title>
                <a :href="item.link" style="text-decoration:none; ">
                {{ item.title }}
                </a></v-list-tile-title>
        </v-list-tile-content>
        </v-list-tile>   
    </v-list>
    </v-menu>
</v-toolbar>
</template>

<script>
export default {
  data: () => ({
    isTransparent: true,    
    titulo : 'Portafolio miguelo',
    menu: [
        { icon: 'home', title: 'inicio' , link :'/' },
        { icon: 'code', title: 'proyectos' , link:'#proy' },
        { icon: 'start', title: 'servicios' , link:'#serv' },
        { icon: 'account_box', title: 'acerca de mi' , link:'#about' },
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
