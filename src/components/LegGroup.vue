<template>  
  <g v-on:click="setSelectRun(index)" v-bind:class="isActive ? 'selected' : ''" class="leg-group" :transform="'translate(' + group.transform + ')'"><path class="leg__path" :d="group.legPath">'
    </path><ellipse class="circle" :cx="group.ellipse.first.cx" :cy="group.ellipse.first.cy" :rx="group.ellipse.rad" :ry="group.ellipse.rad">
    </ellipse><ellipse class="circle" :cx="group.ellipse.second.cx" :cy="group.ellipse.second.cy" :rx=" group.ellipse.rad " :ry="group.ellipse.rad">
    </ellipse><circle class="marker" :cx="group.marker.cx" :cy="group.marker.cy" :r="group.marker.r"></circle><text><tspan :x="group.tspan.x" :y="group.tspan.y">{{ runs[index].leg }}</tspan></text>
  </g>
</template>

<script>
export default {
  props: [
    'index',
    'group',
    'runs',
    'isActive',
    'selectedRun'
  ],
  methods: {
    setSelectRun: function (event) {
      this.selectedRun = event
    }
  }
}
</script>