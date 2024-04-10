<script>
import Axios from 'axios';
import { store } from '../store';

export default {
  name: 'ContactForm',
  components: {
  
  },
  data() {
    return {
        store,
        name: '',
        email: '',
        message: '',
        errors: {},
        success: false
    }
  },
  methods: {
    sendForm(){

        const data = {
            name: this.name,
            email: this.email,
            message: this.message
        }

        this.errors = {};

        Axios.post(`${this.store.apiBaseUrl}/api/contacts`, data)
           .then( res => {

            this.success = res.data.success;

            if( !this.success){

                this.errors = res.data.errors

            } else{

                this.name = ''
                this.email = ''
                this.message = ''
            }
           })
    }
  },
  mounted() {
  }
}

</script>

<template>
<div>
    <h2> contact form</h2>

    <div class="alert alert-succes" v-if="success" role="alert">
    messaggio inviato correttamente
    </div>

    <div class="" >
        <form @submit.prevent="sendForm()">

        <div class="mb-3">
            <input 
            type="text" 
            class="form-control" 
            :class="{'is-invalid': errors.name}"
            name="name"
            placeholder="inserisci il tuo nome"
            v-model="name">

            <p v-for="(error, index) in errors.name" :key='`message-errors-${index}`'
            class="invalid-feedback">
            {{ error }}
            </p>
        </div>

        <div class="mb-3">
            <input 
            type="email" 
            class="form-control" 
            :class="{'is-invalid': errors.email}"
            name="email"
            placeholder="inserisci il tuo email"
            v-model="email">

            <p v-for="(error, index) in errors.email" :key='`message-errors-${index}`'
            class="invalid-feedback">
            {{ error }}
            </p>
        </div>

        <div class="mb-3">
            <textarea 
            class="form-control" 
            :class="{'is-invalid': errors.message}"
            name="message" 
            id="message" 
            cols="30" 
            rows="10"
            v-model="message">
            </textarea>

            <p v-for="(error, index) in errors.message" :key='`message-errors-${index}`'
            class="invalid-feedback">
            {{ error }}
            </p>
        </div>

        <button class="btn btn-primary" type="submit" >
            send
        </button>
        </form>
    </div>
</div>
</template>

<style scoped></style>