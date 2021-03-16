<template>
  <div>
    <button @click="resta">Restar</button>
    <span> Resulado:{{ result }} </span>
  </div>
</template>
<script>
import { EventBus } from '../event-bus.js'
export default {
  name: 'Restar',
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
    resta () {
      this.result--
      EventBus.$emit('updateResult', this.result)
    }
  }
}
</script>

<style>
</style>
