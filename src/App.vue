<template>
  <div class="app">
    <elevator-shaft
        :floor-count="floorCount"
        :current-floor="currentFloor"
        :next-floor="nextFloor"
        :is-resting="isResting"
    />
    <hall
        :floor-count="floorCount"
        :queue="queue"
        :next-floor="nextFloor"
        :current-floor="currentFloor"
        @addFloor="addFloor"
    />
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
      nextFloor: 1,
      isResting: false
    }
  },
  methods: {
    addFloor (number) {
      if (!this.queue.includes(number)) {
        this.queue.push(number)
      }
    },
    go (queue, current) {
        this.nextFloor = queue.shift();
        setTimeout(() => {
          this.isResting = true;
          setTimeout(() => {
            this.currentFloor = this.nextFloor;
            this.isResting = false;
          },  3000)
        }, Math.abs(current - this.nextFloor)*1000)
    }
  },
  watch: {
    queue: {
      handler(queue) {
        if (this.currentFloor === this.nextFloor && queue.length) {
          this.go(queue, this.currentFloor);
        }
      },
      deep: true
    },
    currentFloor(newValue) {
      if (newValue === this.nextFloor && this.queue.length) {
        this.go(this.queue, newValue);
      }
    }
  }
}

</script>

<style scoped>
  .app {
    display: flex;
  }
</style>