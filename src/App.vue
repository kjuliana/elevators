<template>
  <div class="app">
    <elevator-shaft
        :floor-count="floorCount"
        :current-floor="currentFloor"
        :next-floor="nextFloor"
    />
    <hall :floor-count="floorCount" :queue="queue" @addFloor="addFloor"/>
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

      currentFloor: 1,
      queue: [],
      isCarFree: this.currentFloor === this.nextFloor,
      nextFloor: 1
    }
  },
  methods: {
    addFloor (number) {
      if (!this.queue.includes(number)) {
        this.queue.push(number)
      }
    }
  },
  watch: {
    queue: {
      handler(n) {
        if (this.isCarFree && n.length) {
          this.nextFloor = n.shift();
          setTimeout(() => {
            this.currentFloor = this.nextFloor;
          }, Math.abs(this.currentFloor - this.nextFloor)*1000)
        }
      },
      deep: true
    }
  }
}

</script>

<style scoped>
  .app {
    display: flex;
  }
</style>