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
        { hid: 'og:title', property: 'og:title', content: `Character: ${this.name}` },
        { hid: 'og:description', property: 'og:description', content: `About: ${this.name}` },
        { hid: 'og:image', property: 'og:image', content: this.image },
        { hid: `og:image:width`, property: 'og:image:width', content: '1200' },
        { hid: `og:image:height`, property: 'og:image:height', content: '630' },
        { hid: 'og:url', property: 'og:url', content: `${process.env.APP_URL}/character/${this.id}` },
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