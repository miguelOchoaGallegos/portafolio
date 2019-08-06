<template>       
    <v-layout wrap flat>
        <v-flex md4 xs12
            v-for="(hobbi, i) in hobbies"
            :key="i"
            pa-4
        >
        <v-layout row justify-center>
        <span class="tercero--text"><v-icon>{{hobbi.icon}}</v-icon>{{hobbi.desc}}</span>            
        </v-layout>
        </v-flex>
    </v-layout>  
</template>
<script>
export default {
  name: "talento",  
  data: () => ({
    hobbies: [
      { icon : 'dvr', desc: ' Developer'} ,
      { icon : 'web', desc: ' Web designer'} ,
      { icon : 'cloud', desc: ' Cloud computing'} 
    ]
  })
}
</script>
