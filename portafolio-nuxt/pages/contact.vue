<template>
  <section
    id="get-in-touch"
    class="hide-overflow"
  >  
    <a name="contact" />
    <v-layout>
      <v-flex
        hidden-sm-and-down
        md6
      >
        <v-img
          :src="require('@/assets/contact.png')"
          height="100%"
        />
      </v-flex>
      <v-flex
        xs12
        md6
        pa-5        
      >
        <base-bubble-1 />
        <div style="display:none">
          aqui toy
        <Loading :value="dataForm.showLoading" />
        </div>
        <base-heading class="mb-5">
          Contacto
        </base-heading>
        <v-sheet
          max-width="600" 
          color="transparent"         
        >
          <v-form ref="form" id="login-form">
          <v-text-field            
            label="nombre"
            solo
            flat
            v-model="dataForm.name"
            :rules="rules.name"
            required
            @blur="checkValitForm()"
          />          
          <v-text-field            
            label="correo de contacto"
            solo
            flat
            v-model="dataForm.mail"
            :rules="rules.mail"
            required
            @blur="checkValitForm()"
          />          
          <v-text-field            
            label="asunto"
            solo
            flat
            v-model="dataForm.subject"
            :rules="rules.subject"
            required
            @blur="checkValitForm()"
          />          
          <v-textarea            
            label="mensaje"
            solo
            flat
            v-model="dataForm.message"
            :rules="rules.mesage"
            required
            @blur="checkValitForm()"
          />
          </v-form>          
          <v-btn color="secondary" :disabled="dataForm.validate" @click="fetchSomething()">Enviar</v-btn> 
          <base-text>{{messageTest}}</base-text>         
        </v-sheet>
      </v-flex>
    </v-layout>
    
  </section>
</template>
<script>
import {messages} from './const.js';

export default {
  data : () => ({
    messageTest : '',
    rules: { 
      name : [ 
        v => !!v || messages.emptyField+'campo nombre',
        v => v && v.length >= 5 || 'El nombre de usuario debe contener al menos 5 characters'
      ],
      mail : [ 
        v => !!v || messages.emptyField+'correo de contacto',
        v => v &&  v.length>=10  || 'La clave debe contener minimo 10 caracteres.',
        v => {          
            const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
            return pattern.test(v) || 'Correo electronico invalido.';            
        }
      ],
      subject : [ 
        v => !!v || messages.emptyField+'asunto',
        v => v &&  v.length>=5  || 'La clave debe contener minimo 5 caracteres.'
      ],
      mesage : [ 
        v => !!v || messages.emptyField+'mensaje',
        v => v &&  v.length>=5  || 'La clave debe contener minimo 5 caracteres.'
      ]
    },
    dataForm : {
      name:'',
      mail:'',
      subject:'',
      message:'',
      validate : true,
      showLoading : false 
    }
  }),
  components: {
         baseBtn: () => import('@/components/base/Btn'),
         baseHeading: () => import('@/components/base/Heading'),
         baseSubheading: () => import('@/components/base/Subheading'),
         baseText: () => import('@/components/base/Text'),
         baseBubble1: () => import('@/components/base/Bubble1'),
         baseBubble2: () => import('@/components/base/Bubble2'),
         Loading: () => import('@/components/Loading'),
    },
    methods: {
      checkValitForm(){      
        this.dataForm.validate = !this.$refs.form.validate();
      },
      async fetchSomething() {        
        if (!this.$refs.form.validate()) return;   
        this.dataForm.showLoading=true;
        setTimeout(() => this.dataForm.showLoading=false, 3000);

        const message = await this.$axios.$get(`/test`).then((res) => {        
          this.messageTest = '';
          
        });
      }
    }
}
</script>
