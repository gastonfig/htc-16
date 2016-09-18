<template>
  <svg v-if="graphData[index - 1]" class="stats-graph" viewBox="0 0 16 20" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <g id="bars">
      <rect v-bind:class="selectedRun === $index ? 'selected' : ''" :x="$index * 6" width="4" :y="20 - graphData[index - 1][$index]" :height="graphData[index - 1][$index]" v-for="item in runs"></rect>
    </g>
  <svg>
</template>

<script>
export default {
  props: [
    'selectedRun',
    'runs',
    'index'
  ],
  data: function () {
    return {
      graphData: [
        [24, 17.57142857, 30],
        [27.90170132, 26.65406427, 30],
        [22.13677488, 15.56679085, 30],
        [7.68907563, 6.932773109, 30]
      ]
    }
  }
}
</script>