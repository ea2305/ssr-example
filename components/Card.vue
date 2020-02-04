<template>
  <div class="card">
    <div class="card-header">
      <title>item.name</title>
    </div>
    <div class="card-content">
      <p class="is-size-6">id: {{ item.id }}</p>
      <br/>
      <p class="is-size-5">Planet: {{ item.origin.name }}</p>
      <br/>
      <p class="is-size-5">Species: {{ item.species }}</p>
      <br/>
      <a class="button is-info" :href="`/character/${item.id}`">Ver más</a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      default: {}
    }
  }
}
</script>

<style>

</style>