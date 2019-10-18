<template>
  <div id="app">
    <FormTest/>
    <TableTest/>
  </div>
</template>

<script>
import TableTest from './components/TableTest.vue'
import FormTest from './components/FormTest.vue'

export default {
  name: 'app',
  components: {
    TableTest,
    FormTest
  }
}
</script>

<style>
</style>
