<template>
  <div class="shaft">
    <elevator-floor v-for="n in floorCount"/>
    <elevator-car
        :current-floor="currentFloor"
        :next-floor="nextFloor"
        :is-resting="isResting"
    />
  </div>
</template>

<script>
import ElevatorFloor from "./ElevatorFloor.vue";
import ElevatorCar from "./ElevatorCar.vue";

export default {
  name: "ElevatorShaft",
  components: {
    ElevatorFloor,
    ElevatorCar
  },
  props: {
      floorCount:Number,
      currentFloor: Number,
      nextFloor: Number,
      isResting: Boolean
  }

}
</script>

<style scoped>
  .shaft {
    width: 100px;
    border: 2px solid black;
    display: flex;
    flex-direction: column-reverse;
    position: relative;
  }
</style>