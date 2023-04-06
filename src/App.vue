<template>
  <div class="app">
    <elevator-shaft :floor-count="params.floorCount"/>
    <hall :floor-count="params.floorCount"/>
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
      params: {
        floorCount: 5,
        elevatorCount: 1,
      },
      currentFloor: 1
    }
  },
  methods: {

  }
}

</script>

<style scoped>
  .app {
    display: flex;
  }
</style>