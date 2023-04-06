<template>
  <div class="app">
    <elevator-shaft :floor-count="floorCount" :current-floor="currentFloor"/>
    <hall :floor-count="floorCount" @addFloor="addFloor"/>
  </div>
</template>

<script>
import ElevatorShaft from "./components/ElevatorShaft.vue";
import Hall from "./components/Hall.vue";

export default {
  components: {
    ElevatorShaft,
    Hall
  },
  data () {
    return {
      floorCount: 5,
      elevatorCount: 1,
      currentFloor: 1
    }
  },
  methods: {
    addFloor (number) {
      this.currentFloor = number;
    }
  }
}

</script>

<style scoped>
  .app {
    display: flex;
  }
</style>