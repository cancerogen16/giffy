<template>
  <div class="gif" :style="`background-image: url(${gif.images.original.url})`"></div>
</template>

<script>
export default {
    name: "GifItem",
    props: {
        gif: Object
    }
}
</script>

<style scoped>
  .gif {
    width: 240px;
    height: 240px;
    background-repeat: no-repeat;
    background-size: cover;
    margin-bottom: 20px;
  }
</style>