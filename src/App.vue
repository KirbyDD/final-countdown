<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Welcome to Final-Countdown</h1>
      <p>Enter search criteria to display photos.</p>
      <input placeholder="search" />
      <button v-on:click="handleSubmit">Submit</button>
    <PhotoContainer msg="Working"/>
  </div>
</template>

<script>
import PhotoContainer from './components/PhotoContainer.vue'

export default {
  name: 'app',
  components: {
    PhotoContainer
  },
  data() {
    return {
      photos: []
    }
  },
  methods: {
    handleSubmit: (e) => {
      const searchText = e.target.previousSibling.value
      const url = 'https://api.unsplash.com/search/photos/?query=' + searchText + '&client_id=c6eeeedc8c658881d7eba602b260a5faeaed1be2144c5827eaf628940b049428'
      fetch(url)
      .then(response => response.json())
      .then(data => console.log(data))
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
