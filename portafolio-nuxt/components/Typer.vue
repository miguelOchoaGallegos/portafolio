<template>
<v-layout 
    justify-center
    column
    align-center>
    <v-flex         
        text-xs-center        
        xs12> 
        <vue-typer
              :text='typerText'
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
</template>
<script>
import { VueTyper } from 'vue-typer';

export default {
    components: {        
        VueTyper
    },
    props: {
        typerText: '',
    }
}
</script>
<style>

.vue-typer {
  font-family: monospace, 'Helvetica Neue', Helvetica, sans-serif;
  font-size: 25px;
}
.vue-typer .custom.char.typed {
  color: #000;
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
