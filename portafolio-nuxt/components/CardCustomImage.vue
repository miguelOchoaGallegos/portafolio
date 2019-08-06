<template>       
    <v-layout wrap flat class="justify-center">
      <v-card flat style="border:solid #b9b9b9 1px;">
        <v-card-title tercero-title class="justify-center">            
            <v-flex sm12 xs12>
                <v-layout row justify-center>                         
                    
                        <v-img
                        :src="require(`@/assets/works/${path}`)"                  
                        max-width="300"
                        max-height="300"
                        to="http://www.google.com.pe"
                        />
                    
                      
                </v-layout>            
            </v-flex>
            <v-flex sm12 xs12>  
                <v-layout row justify-center> 
                        {{title}}
                </v-layout>                 
                <v-layout row justify-center>                         
                        <a v-bind:href="link" target="_blank">ver</a>
                </v-layout>
            </v-flex> 
        </v-card-title>
        <v-card-text class="dark--text">
            <v-layout style="text-align: center;"> 
            {{message}}
            </v-layout>
            </v-card-text>
      </v-card>
    </v-layout>  
</template>
<script>
export default {
  name: "cardImage",  
  props: {
        path: {type: String, default: ''},
        title: {type: String, default: ''},
        message: {type: String, default: ''},
        link : {type: String, default: ''}
    }
}
</script>
<style>

</style>

