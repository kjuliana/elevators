<template>
  <div class="hall">
    <div class="hall-floor" v-for="n in floorCount">
        <hall-button :number="n" @addFloor="addFloor" />
    </div>
  </div>
</template>

<script>
import HallButton from "./HallButton.vue";

export default {
  name: "Hall",
  components: {
    HallButton
  },
  props: {
    floorCount: {

    }
  },
  methods: {
    addFloor (number) {
      this.$emit('addFloor', number)
    }
  }
}
</script>

<style scoped>
  .hall {
    width: 50px;
    display: flex;
    flex-direction: column-reverse;
    position: relative;
  }
  .hall-floor {
    width: 100%;
    height: 152px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>