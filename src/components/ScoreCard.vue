<template>
  <div>
    <div>{{ score }}</div>
    <button @click="pointUp">+</button>
    <button @click="pointDown">-</button>
  </div>
</template>

<script>
export default {
  props: ["score"],

  methods: {
    pointUp() {
      this.$emit("pointUp", this.score);
    },
    pointDown() {
      this.$emit("pointDown", this.score);
    },
  },
};
</script>

<style>
</style>