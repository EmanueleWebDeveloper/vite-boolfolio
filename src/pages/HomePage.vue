<template>
  <div class="home-page">
    <header>
      <h1>Benvenuti nel mio Portfolio</h1>
      <p>Sono Emanuele Luca Cali', un Web Developer appassionato e creativo.</p>
    </header>
    <section class="about-me">
      <h2>Chi Sono</h2>
      <p>Ciao! Sono un web developer che si occupa della creazione di siti web responsive e funzionali. Mi piace lavorare su progetti stimolanti e sfidanti, dando vita alle idee dei miei clienti attraverso il codice.</p>
    </section>
    <section class="skills">
      <h2>Competenze</h2>
      <ul>
        <li>HTML5</li>
        <li>CSS3 / SASS</li>
        <li>JavaScript</li>
        <li>Vue.js</li>
        <li>Bootstrap / Tailwind CSS</li>
        <li>Responsive Design</li>
        <li>Version Control (Git)</li>
        <li>UI/UX Design</li>
      </ul>
    </section>
    
    <footer>
      <p>Contattami per discutere il tuo prossimo progetto!</p>
      <ul class="social-links">
        <li><a href="https://www.linkedin.com/in/emanuele-luca-cali-952399272/" target="_blank">LinkedIn</a></li>
        <li><a href="https://github.com/EmanueleWebDeveloper?tab=repositories" target="_blank">GitHub</a></li>
        <!-- Aggiungi altri link ai tuoi social media se lo desideri -->
      </ul>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
   
    }
  },
  methods: {
  
  }
}
</script>

<style scoped>

.home-page {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

header {
  text-align: center;
  margin-bottom: 40px;
}

.about-me,
.skills,
.portfolio {
  margin-bottom: 20px;
}

h2 {
  color: #333;
}

ul {
  list-style-type: none;
  padding: 0;
}

footer {
  text-align: center;
}

.social-links li {
  display: inline;
  margin-right: 10px;
}

.social-links li:last-child {
  margin-right: 0;
}
</style>
