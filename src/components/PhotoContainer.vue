<template>
  <main class="hello">
    <h2>Working</h2>
    <section v-bind:key="photo.id" v-for="photo in photos">
      <Photo v-bind:photo="photo"/>
    </section>
  </main>
</template>

<script>
import Photo from "./Photo"

export default {
  name: 'PhotoContainer',
  props: {
    photos: Array
  },
  components: {
    Photo
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
