<template>
  <nav class="box has-text-centered">
    <button class="button is-dark" @click="updatePage(-1)">prev</button>
    <span>|</span>
    <button class="button is-dark" @click="updatePage(1)">next</button>
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