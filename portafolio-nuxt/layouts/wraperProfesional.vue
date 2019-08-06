<template>
    <v-app style="background-color:#fff" v-scroll="onScroll" >    
    <Navbar />     
    <a name="ini" />
    <v-layout row wrap>
    <v-flex xs12 sm12>
    <v-parallax
    id="parallax-hero"
    dark
    style="background-color:#000;"   
    height="100%" 
  >
    <v-layout
      align-center
      column
      justify-center
      style="padding: 10% 0px 0px 0px;"
    >
      <h1 class="display-3 font-weight-thin mb-4">Bienvenido!</h1>      
          <v-layout 
    justify-center
    column
    align-center>
    <v-flex         
        text-xs-center        
        xs12> 
        <vue-typer
              :text='["soy miguel !","fullstack developer","freelance","java lover"]'
              :repeat='Infinity'
              :shuffle='false'
              initial-action='typing'
              :pre-type-delay='70'
              :type-delay='70'
              :pre-erase-delay='2000'
              :erase-delay='250'
              erase-style='select-all'
              :erase-on-complete='false'
              caret-animation='blink'              
            ></vue-typer>
    </v-flex>          
    </v-layout> 
    <v-icon size="45" class="white--text">keyboard_arrow_down</v-icon>
    </v-layout>
  </v-parallax>
    </v-flex>
    </v-layout>
    
  <v-layout fixed-tabs>          
        <v-btn 
        class="secundary"
        @click="redirectPage('#ini')"
        v-show="!isTransparent" fab fixed bottom right><v-icon>keyboard_arrow_up</v-icon></v-btn>
    </v-layout>
  <nuxt />
<v-footer app color="tercero">
    <v-layout
      justify-center
      row
      wrap      
    >     
      <v-flex
        tercero        
        py-0
        text-xs-center
        white--text
        xs12
      >
        &copy;{{ new Date().getFullYear() }} :: <strong> Todos los derechos reservados -  portafolio miguelo</strong>
      </v-flex>
    </v-layout>
  </v-footer>

    </v-app>  
</template>
<script>
import { VueTyper } from 'vue-typer';
// http://theme.srbthemes.com/elvish/index_18.html
export default {
    components: {
        Navbar: () => import('@/components/Navbar'),
        contact: () => import('@/pages/contact') ,
        VueTyper
    },
    data : () =>({
        fixed: false,
        isTransparent: true,
        media:true        
    }),
    mounted() {
      document.getElementById('parallax-hero').style.height = '100vh';
    },
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
<style>

.bg-image {
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
  background-position: center center;  
}

.intro {
  height: 100vh;
  position: relative;
  color: #fff;
}

.intro .intro-content {
  text-align: center;
  position: absolute;
}

.intro .overlay-itro {
  background-color: rgba(0, 0, 0, 0.6);
  position: absolute;
  top: 0;
  left: 0px;
  padding: 0;
  height: 100%;
  width: 100%;
  opacity: .9;
}

.intro .intro-title {
  color: #fff;
  font-weight: 600;
  font-size: 3rem;
}

.intro .intro-subtitle {
  font-size: 1.5rem;
  font-weight: 300;
}

.intro .text-slider-items {
  display: none;
}

.intro-single {
  height: 350px;
}

.intro-single .intro-content {
  margin-top: 30px;
}

.intro-single .intro-title {
  text-transform: uppercase;
  font-size: 3rem;
}

.intro-single .breadcrumb {
  background-color: transparent;
  color: #1976d2;
}

.intro-single .breadcrumb .breadcrumb-item:before {
  color: #cde1f8;
}

.intro-single .breadcrumb .breadcrumb-item.active {
  color: #cde1f8;
}

.intro-single .breadcrumb a {
  color: #fff;
}

.application{
  font-family: 'Montserrat', sans-serif !important;
}

/* typer style*/

.vue-typer {
  font-family: 'Montserrat', sans-serif;
  font-size: 25px;
}
.vue-typer .custom.char.typed {
  color: #fff;
}
.vue-typer .custom.char.selected {
  color: #000;
}

.vue-typer .custom.caret {
  animation: rocking 1s ease-in-out 0s infinite;
}
.vue-typer .custom.caret.typing {
  background-color: #fff;
}
.vue-typer .custom.caret.selecting {
  display: inline-block;
  background-color: #ce0d0d;
}

</style>
