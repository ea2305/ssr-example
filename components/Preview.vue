<template>
  <div class="card">
    <div class="card-content has-text-centered">
      <h1 class="title">{{ name }}</h1>
      <img :src="image" :alt="name" height="200">
      <p class="is-size-5">Status: {{ status }}</p>
      <p class="is-size-5">Species: {{ species }}</p>
      <p class="is-size-5">Type: {{ type }}</p>
      <p class="is-size-5">Gender: {{ gender }}</p>
      <hr/>
      <p class="is-size-5">Origin: {{ origin.name }}</p>
      <p class="is-size-5">Location: {{ location.name }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: ''
    },
    image: {
      type: String,
      default: ''
    },
    status: {
      type: String,
      default: ''
    },
    species: {
      type: String,
      default: ''
    },
    type: {
      type: String,
      default: ''
    },
    gender: {
      type: String,
      default: ''
    },
    origin: {
      type: Object,
      default: { name: '' }
    },
    location: {
      type: Object,
      default: { name: '' }
    },
  }
}
</script>

<style>

</style>