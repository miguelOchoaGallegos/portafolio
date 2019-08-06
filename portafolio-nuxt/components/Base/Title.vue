<template> 
  <v-layout row justify-center pa-2>          
    <h1 class="tercero--text">{{valueString}}</h1>      
  </v-layout>
</template>
<script>
export default {
  name: "title",        
        props: {
            valueString: {type: String, default: ''}            
        }
}
</script>
<style>    

</style>


