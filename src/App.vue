<script>

  import axios from 'axios'
  import ProjectCard from './components/ProjectCard.vue'

  export default ({
    components: {
      ProjectCard
    },
    data () {
      return {
        projects: []
      }
    },
    methods: {
      fetchProjects(page) {
        axios.get('http://127.0.0.1:8000/api/projects', {
          params: {
            page: page
          }
        }) 
        .then(res => {
          

          const results = res.data.results

          this.projects = results.data

          console.log(this.projects)
        })
        .catch(err => {
          console.log(err)
        })
      }
    },
    mounted() {
      this.fetchProjects(1)
    }
  })

</script>

<template>

    <div class="posts">
      <ProjectCard v-for="project in projects" :key="project.id" :project="project" />
    </div> 

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
