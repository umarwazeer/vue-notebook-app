<template>
  <div class="body">
  <Notebook/>
  </div>
</template>

<script>
import Notebook from './components/Notebook.vue'

export default {
  name: 'App',
  components: {
    Notebook
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.body{
  background-color: #c0c2c5;
}
</style>
