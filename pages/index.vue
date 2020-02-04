<template>
  <div class="container">
    <h1>Charaters</h1>

    <List :items="results" />

    <Pagination @pageChange="pageChange"/>
  </div>
</template>

<script>
import List from '~/components/ListView'
import Pagination from '~/components/Pagination'


export default {
  async asyncData ({ app }) {
    const params = { page: 0 }
    let { data } = await app.$axios.get('/character', { params })
    return data
  },
  components: {
    List,
    Pagination
  },
  data: () => ({
    page: 1
  }),
  methods: {
    async fetch (page) {
      let { data } = await this.$axios.get(`/character`, { params: { page }})
      this.info = data.info
      this.results = data.results
    },
    pageChange (change) {
      let newPage = this.page + change
      this.fetch(newPage)
      this.page = newPage
    }
  }
}
</script>