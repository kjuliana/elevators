<template>
  <div
      :style="'bottom:' + (nextFloor - 1)*151 + 'px; transition-duration: ' + Math.abs(nextFloor-currentFloor) + 's'"
      class="car"
      :class="{'car-resting' : isResting}"
  >
    <div
        class="indicator"
        v-if="nextFloor !== currentFloor && !isResting"
    >
      {{nextFloor + ' ' + (currentFloor - nextFloor > 0 ? '⬇️' : '⬆️')}}
    </div>
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
    isResting: Boolean
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
    transition: bottom 3s ease-in-out;
    display: flex;
    justify-content: center;
  }

  .car-resting {
    background-color: rgba(0, 151, 167, 0.52);
  }

  .indicator {
    color: white;
  }
</style>