<template>
  <div
      :style="'bottom:' + (nextFloor - 1)*151 + 'px; transition-duration: ' + Math.abs(nextFloor-currentFloor) + 's'"
      class="car"
  >

  </div>
</template>

<script>
export default {
  name: "ElevatorCar",
  data () {
    return {

    }
  },
  props: {
    currentFloor: Number,
    nextFloor: Number,
  },
  methods: {

  }
}
</script>

<style scoped>
  .car {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 151px;
    background-color: #0097a7;
    transition: bottom 3s linear;
  }
</style>