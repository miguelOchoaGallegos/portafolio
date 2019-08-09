<template>   
<section  
  class="hide-overflow">
  <a name="contact" />     
    <v-layout wrap>     
      <div style="display:none">
      <Loading :value="dataForm.showLoading" /> 
      </div>
      <v-flex
        xs12
        md3
        mb3      
      >      
      <baseTitle valueString='Otros medios para comunicarnos !!' />
      <v-layout row  justify-center>        
      <contactPiece
        title="Llamando a" 
        message="+51 941 499 556"   
        icon="mobile_friendly"
        xs12
      />    
      </v-layout>
      <v-layout row  justify-center>
      <contactPiece
        title="Escribiendo a" 
        message="miguel.ochoa.gallegos@gmail.com"
        icon="mail_outline"
        xs12
      />
      </v-layout>
      
    

      </v-flex>
      <v-flex
        xs12
        md9
        mb9        
      >         
      <baseTitle valueString='Estoy en contacto vía correo' />          
      <baseText valueString='Ingresa tus datos para entrar en contacto de necesitar alguna ayuda !!' />
        <v-card class="pa-5">
          <v-form ref="form" id="login-form">
          <v-text-field            
            label="nombre"
            v-model="dataForm.name"
            :rules="rules.name"
            required
            @blur="checkValitForm()"
          />          
          <v-text-field            
            label="correo de contacto"            
            v-model="dataForm.mail"
            :rules="rules.mail"
            required
            @blur="checkValitForm()"
          />          
          <v-text-field            
            label="celular"            
            v-model="dataForm.phone"
            :rules="rules.phone"
            required
            maxLength="9"
            mask="#########"
            @blur="checkValitForm()"
          />          
          <v-textarea            
            label="mensaje"            
            v-model="dataForm.message"
            :rules="rules.mesage"
            required
            @blur="checkValitForm()"
          />
          </v-form> 
          <v-btn color="tercero" :disabled="dataForm.validate" @click="enviarMail()">Enviar</v-btn> 
          <base-text v-if="dataForm.showSuccess" class="mb-12 success--text">
            Mensaje enviado satisfactoriamente !! 
          </base-text>
        </v-card>
      </v-flex>
    </v-layout>        
  </section>    
</template>
<script>
import {messages} from '../components/const.js';

export default {
  data : () => ({
    messageTest : '',
    rules: { 
      name : [ 
        v => !!v || messages.emptyField+'campo nombre',
        v => v && v.length >= 5 || 'El nombre de usuario debe contener al menos 5 carácteres'
      ],
      mail : [ 
        v => !!v || messages.emptyField+'correo de contacto',
        v => v &&  v.length>=10  || 'La clave debe contener mínimo 10 carácteres.',
        v => {          
            const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
            return pattern.test(v) || 'Correo electrónico inválido.';
        }
      ],
      phone : [ 
        v => !!v || messages.emptyField+'telefono',
        v => v &&  v.length==9  || 'El número de celular debe contener 9 carácteres.'        
      ],
      mesage : [ 
        v => !!v || messages.emptyField+'mensaje',
        v => v &&  v.length>=5  || 'El mensaje debe contener mínimo 5 carácteres.'
      ]
    },
    dataForm : {
      name:'',
      mail:'',
      phone:'',
      message:'',
      validate : true,
      showLoading : false,
      showSuccess:false
    }
  }),
  components: {                  
         Loading: () => import('@/components/Loading'),
         baseText: () => import('@/components/base/Text'),
         baseTitle: () => import('@/components/base/Title'),
         contactPiece: () => import('@/components/ContactPiece')
    },
    methods: {
      checkValitForm(){      
        this.dataForm.validate = !this.$refs.form.validate();        
      },
      async enviarMail() {        
        if (!this.$refs.form.validate()) return;   
        this.dataForm.showLoading=true;        
        let payload = {};        
        await setTimeout(() => {
        payload.mail =this.dataForm.mail;
        payload.phone =this.dataForm.phone;
        payload.username =this.dataForm.name;
        payload.text =this.dataForm.message;        
        this.$axios.$post(`/send`, payload).then((res) => {          
          this.dataForm.showLoading=false;
          this.dataForm.showSuccess=true;          
        }); 
        } , 3000);
        
      }
    }
}
</script>
<style>
.wrapper-shadow{
    box-shadow: 0 1px 1px 0 rgba(0, 0, 0, 0.06), 0 2px 5px 0 rgba(0, 0, 0, 0.2);
}
.wrapper-img {    
    font-size: 2rem;    
    line-height: 1.55;
    margin: 0 auto;
    text-align: center;
    box-shadow: 0 0 0 10px #1976d2;
    display: block;
}
.footer-paralax { 
    padding: 4rem 0 0 0;
}
.sect-mt4 {
    margin-top: 4rem;
}
.paralax-mf {
    position: relative;
    padding: 8rem 0;
}
.bg-image {
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
    background-position: center center;    
}
</style>
