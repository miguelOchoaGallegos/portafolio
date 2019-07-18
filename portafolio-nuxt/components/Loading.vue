<template>
 <v-app id="loading">
  <v-layout row justify-center>
    <v-dialog v-model="value" persistent content content-class="centered-dialog">
      <v-container fill-height>
        <v-layout column justify-center align-center>
          <v-progress-circular indeterminate :size="70" :width="7" :color="progressColor"></v-progress-circular>
          <h2 v-if="message != null">{{message}}</h2>
        </v-layout>
      </v-container>
    </v-dialog>
  </v-layout>
   </v-app>
</template>
<script>
export default {
  name: "loading",
        data: function () {
            return {}
        },
        props: {
            value: {type: Boolean, default: false},
            message: {type: String, default: 'enviando ...'},
            progressColor: {type: String, default: '#ff8f00'},
        },
}
</script>
<style>    
.dialog.centered-dialog,
.v-dialog.centered-dialog
 {
    background: #282c2dad;
    box-shadow: none;
    border-radius: 6px;
    width: auto;
    color: whitesmoke;
  }
</style>


