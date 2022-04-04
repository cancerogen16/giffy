<template>
  <gif-item v-for="gif in gifs" :key="gif.id" :gif="gif" />
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

</style>