<template>
  <article>
    <img :src="photo.urls.regular" />
  </article>
</template>

<script>
export default {
  name: "Photo",
  props: ['photo']
}
</script>

<style scoped>

</style>


