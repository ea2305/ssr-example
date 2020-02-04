<template>
  <nav>
    <button @click="updatePage(-1)">prev</button>
    <span>|</span>
    <button @click="updatePage(1)">next</button>
  </nav>
</template>

<script>
export default {
  props: {
    pageChange: {
      type: Function,
      default: () => {}
    }
  },
  methods: {
    updatePage (change) {
      this.$emit('pageChange', change)
    }
  }
}
</script>

<style>

</style>