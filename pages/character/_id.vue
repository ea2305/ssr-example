<template>
  <div class="container">

    <h1>{{ name }}</h1>
    <img :src="image" :alt="name" height="200">
    <p>Status: {{ status }}</p>
    <p>Species: {{ species }}</p>
    <p>Type: {{ type }}</p>
    <p>Gender: {{ gender }}</p>
    <p>Origin: {{ origin.name }}</p>
    <p>Location: {{ location.name }}</p>

  </div>
</template>

<script>
export default {
  head () {
    return {
      title: `About: ${this.name}`,
      meta: [
        { property: 'og:title', content: `Character: ${this.name}` },
        { property: 'og:description', content: `About: ${this.name}` },
        { property: 'og:image', content: this.image },
        { property: 'og:url', content: `http://localhost:3000/character/${this.name}` },
      ]
    }
  },
  async asyncData ({ app, route }) {
    let { id } = route.params
    let { data } = await app.$axios.get(`/character/${id}`)
    return data
  }
}
</script>

<style>

</style>