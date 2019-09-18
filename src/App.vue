<template>
  <div>
    <img src="https://wallpapermemory.com/uploads/654/gallery-background-hd-1920x1200-193325.jpg"  class="background"/>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <h1>Welcome to Final-Countdown</h1>
      <h2>Enter search criteria to display photos.</h2>
      <div class='search'>
      <input placeholder="Search..." :value="searchValue" v-on:change="handleChange"/>
      <button v-on:click="handleSubmit">Submit</button>
      </div>
    <PhotoContainer v-bind:photos='photos'/>
  </div>
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
      photos: [],
      searchValue: ""
    }
  },
  methods: {
    handleSubmit() {
      const searchText = this.searchValue;
      const url = 'https://api.unsplash.com/search/photos/?query=' + searchText + '&client_id=c6eeeedc8c658881d7eba602b260a5faeaed1be2144c5827eaf628940b049428'
      fetch(url)
      .then(response => response.json())
      .then(data => this.photos = data.results)
      this.searchValue = ''
    },
    handleChange(e) {
      this.searchValue = e.target.value
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
  color: #fff;
}

h1 {
  color: white;
  margin-top: 0px;
}

body {
  margin: 0px;
}

input {
  font-size: 2rem;
  height: 50px;
  width: 35%;
}

button {
  font-size: 1rem;
  height: 56px;
  width: 80px;
}

.background {
  height: 100%;
  position: fixed;
  filter: brightness(25%);
  width: 100%;
  z-index: -1;
}

.search {
  display: flex;
  justify-content: center;
}
</style>
