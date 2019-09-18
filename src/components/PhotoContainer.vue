<template>
  <main class="container">
    <section v-bind:key="photo.id" v-for="photo in photos">
      <Photo v-bind:photo="photo"/>
    </section>
  </main>
</template>

<script>
import Photo from "./Photo";

export default {
  name: "PhotoContainer",
  props: {
    photos: Array
  },
  components: {
    Photo
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  align-items: center;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>
