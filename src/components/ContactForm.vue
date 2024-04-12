<script>
import axios from 'axios'

import {store} from '../store.js'

export default {
    name: 'ContactForm',
    components: {

    },
    data() {
        return {
            store,
            name:'',
            email:'',
            message:'',
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

            this.errors={}

            axios.post(`${this.store.apiBaseUrl}/api/contacts`, data)
            .then( res => {
                this.success = res.data.success
                if(!this.success) {
                    this.errors = res.data.errors
                } else {
                    this.name='',
                    this.email='',
                    this.message=''
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
        <h1 class="text-center mt-4">Contattami:</h1>

        <div class="alert alert-success" v-if="success" role="alert">
            Messaggio inviato correttamente
        </div>
    </div>

    <div>
        <form @submit.prevent="sendForm()">
            <div class="mb-3">
                <input type="text" class="form-control" :class="{'is-invalid': errors?.name}" name="name" placeholder="Inserisci il tuo nome e cognome" v-model="name">
                <p v-for="(error, index) in errors?.name" :key='`message-errors-${index}`' class="invalid-feedback"> {{ error }}</p>
            </div>

            <div class="mb-3">
                <input type="email" class="form-control" :class="{'is-invalid':errors?.email}" name="email" placeholder="Inserisci la tua e-mail" v-model="email">
                <p v-for="(error, index) in errors?.email" :key='`message-errors-${index}`' class="invalid-feedback"> {{ error }}</p>
            </div>

            <div class="mb-3">
                <textarea class="form-control" :enter-class="{'is-invalid':errors?.message}" name="message" id="message" cols="30" rows="10" v-model="message"></textarea>
                <p v-for="(error, index) in errors?.message" :key='`message-errors-${index}`' class="invalid-feedback"> {{ error }}</p>
            </div>

            
            <div class="text-center">
                <button class="btn btn-primary" type="submit">INVIA</button>
            </div>
        </form>
    </div>
</template>



<style scoped></style>