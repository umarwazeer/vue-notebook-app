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
  text-align: left;
  /* background: #F3F3F3; */
  /* color: #F3F3F3; */
  margin-top: 20px;
}
.body{
  /* background-color: #f3f3f3; */
}
</style>
