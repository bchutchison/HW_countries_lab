<template lang="html">

  <select v-on:change="onChange" v-model="country">
    <option v-for="(country, index) in countries" :country="country" :key="index">{{country.name}}</option>
  </select>

  <!-- <option on-change:click="handleClick">{{country.name}}</option> -->
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'country-select',
  props: ['countries', 'country'],
  methods: {
    onChange() {
      eventBus.$emit('country-selected', this.country)
      // mutating props
    }
  }
}
</script>

<style lang="css" scoped>
</style>
