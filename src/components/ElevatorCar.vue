<template>
  <div :style="'bottom:' + (currentFloor - 1)*151 + 'px'" class="car"></div>
</template>

<script>
export default {
  name: "ElevatorCar",
  props: {
    currentFloor:{}
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
  }
</style>