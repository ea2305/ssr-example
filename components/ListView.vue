<template>
  <ul class="box">
    <li v-for="item of items" :key="item.id">
      <p> {{ item.name }} </p>
      <span>Planet: {{item.origin.name}}</span>
      <br/>
      <span>Species: {{item.species}}</span>
      <br/>
      <a :href="`/character/${item.id}`">Ver más</a>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    items: {
      type: Array,
      default: []
    }
  }
}
</script>

<style>

</style>