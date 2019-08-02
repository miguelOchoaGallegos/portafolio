<template>
    <v-layout
      text-xs-center
      row      
      pa-3
      wrap      
    >  
    <v-flex xs12 md12 sm12>
    <base-heading tag="h1" class="v-heading dark--text">
        {{titulo}}
    </base-heading>     
    </v-flex>
    <v-flex xs12>
     <base-text class="line-mf" />  
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
},
components: {         
    baseHeading: () => import('@/components/base/Heading'),
    baseSubheading: () => import('@/components/base/Subheading'),
    baseText: () => import('@/components/base/Text')
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
