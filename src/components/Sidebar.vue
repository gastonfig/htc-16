<template>
  <section class="stats__container"> 
    <header>
      <h2>Leg <span v-bind:class="fade ? 'fadeIn' : ''">{{ runs[selectedRun].leg }}</span></h2>
      <nav class="leg-nav">
        <ul>
          <li v-on:click.stop="prevRun()">
            <a href="#"><svg width="8px" height="11px" viewBox="0 0 8 11" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
              <polygon points="7.1834532 9.9510064 6.4970211 10.5932203 0.8165468 5.2966102 6.4970211 0 7.1834532 0.6389036 2.1927271 5.2966102 7.1834532 9.9510064"></polygon>
            </svg></a>
          </li>
          <li v-on:click.stop="nextRun()">
            <a href="#"><svg width="8px" height="11px" viewBox="0 0 8 11" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
              <polygon points="0.8165468 0.8456038 1.5029789 0.2033898 7.1834532 5.5 1.5029789 10.7966102 0.8165468 10.1577066 5.8072729 5.5"></polygon>
            </svg></a>
          </li>
        </ul>
      </nav>      
    </header>

    <div class="stats__list">
      <ul class="stats">
        <navcomp
          v-for="item in runs[selectedRun]"
          :runs="runs"
          :item="item"
          :key="$key"
          :index="$index"
          :graphs="graphs"
          :fade="fade"
          :selected-run="selectedRun"
          v-if="$key !== 'leg'">          
        </navcomp>      
      </ul>
    </div>
  </section>
</template>

<script>
import Navcomp from './Navcomp.vue'

export default {
  props: ['selectedRun', 'runs'],
  components: {
    Navcomp
  },
  methods: {
    setSelectRun: function (event) {
      this.selectedRun = event
    },
    nextRun: function () {
      var selection = this.selectedRun === 2 ? 0 : this.selectedRun + 1
      this.setSelectRun(selection)
    },
    prevRun: function () {
      var selection = this.selectedRun === 0 ? 2 : this.selectedRun - 1
      this.setSelectRun(selection)
    }
  }
}
</script>