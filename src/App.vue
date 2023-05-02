<script>

  import axios from 'axios'

  export default ({
    data () {
      return {
        projects: []
      }
    },
    methods: {
      fetchProjects() {
        axios.get('http://127.0.0.1:8000/api/projects')
        .then(res => {
          console.log(res)
        })
        .catch(err => {
          console.log(err)
        })
      }
    },
    mounted() {
      this.fetchProjects()
    }
  })

</script>

<template>
  CIAO
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
