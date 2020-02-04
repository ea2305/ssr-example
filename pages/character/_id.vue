<template>
  <div class="container">
    <button class="button is-warning is-fullwidth has-text-centered" @click="backPage">Back</button>
    <Preview :name="name" :image="image" :status="status" :species="species" :type="type" :gender="gender" :origin="origin" :location="location"/>

  </div>


</template>

<script>
import Preview from '~/components/Preview'

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
  },
  components: {
    Preview
  },
  methods: {
    backPage () {
      this.$router.go(-1)
    }
  }
}
</script>

<style>

</style>