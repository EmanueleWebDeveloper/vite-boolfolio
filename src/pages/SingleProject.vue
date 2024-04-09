<script>

import axios from 'axios'
import {store} from '../store.js'

export default {
  name: 'SingleProject',
  components: {

  },
  data() {
    return {
      project: [],
      store
    }
  },
  methods: {
    getSingleProject() {

axios.get(`${store.apiBaseUrl}/api/test/${this.$route.params.slug}`)
    .then(res => {
        console.log(res)
        if (res.data.success) {
            this.post = res.data.post
        } else {
            //Redirect alla pagina 404
             this.$router.push({ name: 'not-found' })
        }
    })

}
  },
  mounted() {
    this.getSingleProject()

  }
}

</script>

<template>
  <h1 class="text-center fw-bold mt-5">Visualizza il progetto singolo</h1>
  
  <div class="d-flex justify-content-center">
      <div class="card my-4" style="width: 40rem;">
          <img class="card-img-top" :src='`${store.apiBaseUrl}/storage/${project?.cover}`' alt="card_image"/>

          <div class="card-body my-4">
              <h2 class="card-title text-center fw-bold">{{project?.title}}</h2>
              <p class="card-text text-center">{{project?.content}}</p>
              <p class="card-text"><strong>Tipologia:</strong> {{project.type?.name}}</p>
              
              
              <p class="card-text" v-for="(element, index) in project?.technologies" :key="element.id"><strong>Linguaggi/Framework:</strong> {{ element?.name }}</p>
          </div>
      </div>
  </div>
</template>

<style scoped></style>