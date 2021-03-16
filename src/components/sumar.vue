<template>
  <div>
    <button @click="suma">Sumar</button>
    <span> Resulado:{{ result }} </span>
  </div>
</template>
<script>
import { EventBus } from '../event-bus.js'
export default {
  name: 'Sumar',
  props: {
    result: {
      type: Number,
      default: 0
    }
  },
  /* data() {
      return {
        result: 0
      }
  }, */
  methods: {
    suma () {
      this.result++
      EventBus.$emit('updateResult', this.result)
    }
  }
}
</script>

<style>
</style>
