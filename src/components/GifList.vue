<template>
  <div class="gifList">
      <gif-item v-for="gif in gifs" :key="gif.id" :gif="gif" />
  </div>
</template>

<script>
import GifItem from '@/components/GifItem.vue'

export default {
    name: "GifList",
    components: {GifItem},
    props: {
        gifs: Array
    }
}
</script>

<style scoped>
    .gifList {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }
</style>