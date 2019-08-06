<template>       
    <v-layout wrap flat>
      <v-card flat style="border:solid #b9b9b9 1px;">
        <v-card-title tercero-title class="justify-center">            
            <v-flex sm12 xs12>
                <v-layout row justify-center> 
                        <v-icon            
                            size="52"
                            color="primary"
                            >{{icon}}</v-icon>
                </v-layout>            
            </v-flex>
            <v-flex sm12 xs12>  
                <v-layout row justify-center> 
                        {{title}}
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
  name: "card",  
  props: {
        icon: {type: String, default: ''},
        title: {type: String, default: ''},
        message: {type: String, default: ''},
    }
}
</script>
<style>

</style>

