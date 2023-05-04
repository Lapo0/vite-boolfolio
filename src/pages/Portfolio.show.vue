<template>
    <div class="container">
        <h1>
            {{ slug }}
        </h1>
    </div>
  </template>
  
  <script>
    import axios from 'axios'

    export default {
      props: ['slug'],
      methods: {
        fetchProject() {
            axios.get(`http://127.0.0.1:8000/api/projects/${ this.slug }`)
            .then(res => {
                console.log(res)
            })
            .catch(err => {
                console.log(err)
            })
        }
      },
      created() {
        this.fetchProject()
      },
    }
  </script>
  
  <style scoped>
  </style>