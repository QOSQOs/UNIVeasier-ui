<!-- Add HTML -->
<template>
  <div>
    <p>
      <label>Name</label>
      <input v-model="name">
    </p>
    
    <p>
      <label>Age</label>
      <input v-model.number="age">
    </p>

    <p>
      <label>Email</label>
      <input v-model="email">
    </p>
    <button v-on:click="AddTest()">Add</button>
  </div>
</template>


<!-- Add JS code -->
<script>
import axios from 'axios'

export default {
    data(){
      return {
        name: null,
        age: null,
        email: null
      }
    },
    methods: {
      clearData(){
        this.name = null
        this.age = null
        this.email = null
      },
      AddTest(){
        axios.post('/test', {
          name: this.name,
          age: this.age,
          email: this.email
        })
        .then(response => {
          console.log(response.data)
        })
        .catch(error => {
          console.log(error)
        })

        this.clearData()
      }
    }
}
</script>


<!-- Add CSS -->
<style>

</style>
