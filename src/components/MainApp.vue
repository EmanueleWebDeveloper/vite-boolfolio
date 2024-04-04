<script>
import axios from 'axios';
import ProjectCard from '../components/ProjectCard.vue'


export default {
  components: {
    ProjectCard
  },
  name: 'MainApp',
  data() {
    return {
      arrayProjects: [],
      currentPage: '',
      lastPage: ''

    }
  },
  methods: {
    getProjects(apiProjectPage) {

      axios
        .get('http://127.0.0.1:8000/api/test', {
          params: {
            page: apiProjectPage
          }
        })
        .then(response => {
          console.log(response.data.projects.data);

          this.arrayProjects = response.data.projects.data
          this.currentPage = response.data.projects.current_page;
          this.lastPage = response.data.projects.last_page;
        })

    }
  },
  mounted() {
    this.getProjects(1)
  },
}
</script>

<template>

  <main>
    <h2>qui stampo i projects</h2>

    <ProjectCard class="my-3" v-for="(element, index) in arrayProjects" :key="element.id" :title="element.title" :content="element.content" :type="element.type.name" :technologies="element.technologies"/>


<!-- 
    <ul>
      <li v-for=" (element, index) in arrayProjects" :key="element.id">

        <a href="#">{{ element.title }}</a>

      </li>
    </ul> -->


    <nav aria-label="Page navigation example">
      <ul class="pagination">
        <li class="page-item" :class="{ 'disabled': currentPage === 1 }">
          <button class="page-link" @click="getProjects(currentPage - 1)">Previous</button>
        </li>

        <li class="page-item" v-for=" (element, index) in lastPage " :key="index">
          <button class="page-link" @click="getProjects(element)">{{ element }}</button>
        </li>

        <li class="page-item" :class="{ 'disabled': currentPage === lastPage }">
          <button class="page-link" @click="getProjects(currentPage + 1)">Next</button>
        </li>
      </ul>
    </nav>

  </main>

</template>

<style scoped></style>
