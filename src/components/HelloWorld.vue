<template>
  <div class="hello">
   <Sumar :result="result"/>
   <Restar :result="result"/>
  </div>
</template>

<script>
import Sumar from './sumar.vue'
import Restar from './restar.vue'
import { EventBus } from '../event-bus.js'
export default {
  name: 'HelloWorld',
  components: {
    Sumar,
    Restar
  },
  beforeMount () {
    EventBus.$on('updateResult', this.updateResult)
  },
  beforeDestroy () {
    EventBus.$off('updateResult', this.updateResult)
  },
  data () {
    return {
      result: 10
    }
  },
  methods: {
    updateResult (newResult) {
      this.result = newResult
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
