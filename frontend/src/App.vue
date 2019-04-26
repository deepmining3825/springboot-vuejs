<template>
  <div>
    <button @click="callRestService">call</button>
  </div>
</template>

<script>
  // import axios from 'axios'
  import { AXIOS } from './components/http-common.js'
  export default {
    name: 'service',
    data () {
      return {
        msg: 'HowTo call REST-Services:',
        response: [],
        errors: []
      }
    },
    methods: {
      // Fetches posts when the component is created.
      callRestService () {
        AXIOS.get(`/hello`)
                .then(response => {
                  // JSON responses are automatically parsed.
                  this.response = response.data;
                  console.log(response.data)
                })
                .catch(e => {
                  this.errors.push(e)
                })
      }
    }
  }
</script>

<style>

</style>
