<template>
  <button
      class="button"
      :class="{'button-active' : isWaiting}"
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
    number:{
      type: Number
    },
    isWaiting:{}
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
    border: 1px solid #0097a7;
    width: 20px;
    height: 20px;
    border-radius: 50%;
  }
  .button-active {
    border: 1px solid orangered;
  }

</style>