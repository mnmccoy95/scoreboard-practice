<template>
  <div>
    <span :class="{ winning: teams[0].score > teams[1].score }">
      {{ teams[0].name }}
    </span>
    vs.
    <span :class="{ winning: teams[1].score > teams[0].score }">
      {{ teams[1].name }}
    </span>
  </div>
</template>

<script>
export default {
  props: {
    teams: Array,
  },
};
</script>

<style>
.winning {
  color: gold;
}
</style>