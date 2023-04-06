<template>
  <button class="button">
    {{number}}
  </button>
</template>

<script>
export default {
  name: "HallButton",
  props: {
    number: {
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
</style>