<template>       
    <v-layout row>
      <v-card flat style="background-color:transparent">
        <v-card-title tercero-title class="justify-center">            
            <v-flex sm12 xs12>                
                        <v-icon            
                            size="36"
                            color="primary"
                            >{{icon}}</v-icon>
                
            </v-flex>
            <v-flex sm12 xs12 class="tercero--text">{{title}}</v-flex> 
        </v-card-title>
        <v-card-text class="info--text">
            <v-layout style="text-align: center;"> 
            {{message}}
            </v-layout>
        </v-card-text>
      </v-card>
    </v-layout>  
</template>
<script>
export default {
  name: "contact",  
  props: {
        icon: {type: String, default: ''},
        title: {type: String, default: ''},
        message: {type: String, default: ''},
    }
}
</script>
<style>

</style>
