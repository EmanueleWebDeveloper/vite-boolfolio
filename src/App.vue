<script>
// import MainApp from './components/MainApp.vue'

import HeaderApp from './components/HeaderApp.vue'

export default {
  components: {
    HeaderApp
  },
  data() {
    return {

    }
  },
  methods: {

  },
  mounted() {
  }
}

</script>

<template>
  <!-- <h1>Ciao dal Frontend di Boolpress</h1> -->

   <!-- <MainApp/> -->

  <!-- componenti fissi che vengono visualizzati per tutte le pagine -->
  <!-- header -->
  <HeaderApp/>
  <!-- inserisce in modo dinamico il contenuto delle pagine -->
  <router-view></router-view>


</template>

<style scoped></style>