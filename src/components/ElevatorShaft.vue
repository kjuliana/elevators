<template>
  <div class="shaft">
    <elevator-floor v-for="n in floorCount"/>
    <elevator-car/>
  </div>
</template>

<script>
import ElevatorFloor from "./ElevatorFloor.vue";
import ElevatorCar from "./ElevatorCar.vue";

export default {
  name: "ElevatorShaft",
  components: {
    ElevatorFloor, ElevatorCar
  },
  props: {
    floorCount: {

    }
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