<template>
  <ul class="box">
    <li v-for="item of items" :key="item.id">
      <Card :item="item" />
    </li>
  </ul>
</template>

<script>
import Card from '~/components/Card'

export default {
  props: {
    items: {
      type: Array,
      default: []
    }
  },
  components: {
    Card
  }
}
</script>

<style>

</style>