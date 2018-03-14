<template>
  <div class="photo">
    <img :src="photo">
  </div>
</template>

<script>
  export default {
    props: ['photo','marginBottom']
  }
</script>

<style scoped>
  .photo {
    max-width: 100%;
  }

@media (min-width: 1000px) {
  img {
    max-width: 90%;
  }
}

</style>
