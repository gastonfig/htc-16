<template>
  <li>
    <span class="stats__label">{{ key }}:</span> 
    <span class="stats__value">{{ item }}{{ units[key] }}
      <graph :index="index" :runs="runs" :selected-run="selectedRun"></graph>
    </span>
  </li>
</template>

<script>
import Graph from './Graph.vue'

export default {
  props: [
    'item',
    'key',
    'index',
    'selectedRun',
    'runs'
  ],
  components: {
    Graph
  },
  data () {
    return {
      units: {
        'distance': 'mi',
        'pace': '/mi',
        'elevation': 'ft'
      }
    }
  }
}
</script>
