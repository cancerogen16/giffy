<template>
  <input placeholder="Type something to search for awesome gifs" v-model="keyword" @input="onInput">
</template>

<script>
export default {
    name: "GifSearch",
    data() {
      return {
        keyword: '',
        timeout: null,
      }
    },
    methods: {
      onInput() {
        clearTimeout(this.timeout)
        this.timeout = setTimeout(() => {
          this.search()
        }, 500)
      },
      search() {
        fetch(`https://api.giphy.com/v1/gifs/search?api_key=3QIT4DHk8dy5nc3ZQTmRumkz8nhcAqI8&q=${this.keyword}&limit=14`)
          .then(response => response.json())
          .then(result => {
            console.log(result)

            this.gifs = result.data

            this.$emit('fetch-gifs', result.data)
          })
      }
    }
}
</script>

<style scoped>
  input {
    margin: 20px auto;
    padding: 10px 10px;
    border-radius: 4px;
    font-size: 16px;
    width: 100%;
  }

  input:focus {
    border-color: blue;
  }
</style>