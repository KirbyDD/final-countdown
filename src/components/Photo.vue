<template>
  <article>
    <img :src="photo.urls.small" />
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


