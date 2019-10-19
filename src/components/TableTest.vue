<!-- Add HTML -->
<template>
  <div>
    <button v-on:click="getListTest()">List</button>
    <tr>
      <th>ID</th>
      <th>NAME</th>
      <th>AGE</th>
      <th>EMAIL</th>
    </tr>
    <tr v-for="test in tests" :key="test.id">
      <td>{{test.id}}</td>
      <td>{{test.name}}</td>
      <td>{{test.age}}</td>
      <td>{{test.email}}</td>
    </tr>
  </div>
</template>


<!-- Add JS code -->
<script>
import axios from 'axios'

export default {
  data(){
    return {
      tests: null
    }
  },
  mounted() {
    this.getListTest()
  },
  methods: {
    getListTest() {
      axios.get('/test')
      .then( response => {
        this.tests = response.data
      })
      .catch( error => {
        console.log(error)
      })
    }
  }
}
</script>


<!-- Add CSS -->
<style>

</style>
