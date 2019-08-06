<template>
    <v-layout
      text-xs-center
      row      
      pa-5
      wrap      
    >  
    <v-flex xs12 md12 sm12>
    <h1 tag="h1" class="dark--text">
        {{titulo}}
    </h1>     
    </v-flex>
    <v-flex xs12>
     <v-icon class="tercero--text">code</v-icon>
    </v-flex>    
    </v-layout>      
</template>
<script>
export default {   
props: {
titulo: {
    type: String,
    default: '-'
}
}
}
</script>
<style>
.line-mf {
    width: 40px;
    height: 5px;
    background-color: #000;
    margin: 0 auto;
}
</style>
