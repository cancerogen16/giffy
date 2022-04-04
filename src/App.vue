<template>
<gif-search @fetch-gifs="onFetch" />
<gif-list :gifs="gifs" />
</template>

<script>
import GifList from '@/components/GifList.vue'
import GifSearch from '@/components/GifSearch.vue'
export default {
  name: 'App',
  components: {
    GifSearch,
    GifList
  },
  data() {
    return {
      gifs: []
    }
  },
  methods: {
    onFetch(result) {
      this.gifs = result
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
  }
  body {
    padding: 50px;
  }
</style>
