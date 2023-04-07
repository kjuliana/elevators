<template>
  <button
      class="button"
      :class="{'button-waiting' : isWaiting, 'button-active': isWaiting && number === nextFloor}"
      @click="addFloor"
  >
    {{number}}
  </button>
</template>

<script>
export default {
  name: "HallButton",
  data () {
    return {
    }
  },
  props: {
    number: Number,
    isWaiting: Boolean,
    nextFloor: Number
  },
  methods: {
    addFloor () {
      this.$emit('addFloor', this.number)
    }
  }
}
</script>

<style scoped>
  .button {
    border: none;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    color: white;
    background-color: #0097a7;
  }

  .button-waiting {
    background-color: rgba(0, 151, 167, 0.5);
  }

  .button-active {
    background-color: rgba(0, 151, 167, 0.15);
  }

</style>