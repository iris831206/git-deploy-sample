<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ params }}
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      params: {}
    }
  },
  mounted() {
    console.log(import.meta.env.VITE_PATH);
    console.log(import.meta.env.VITE_TEXT);
    axios.get('https://randomuser.me/api/').then((res) => {
      this.params = res.data.results[0]
      console.log(this.params)
    })
  }
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
