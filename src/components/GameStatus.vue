<template>
  <div>{{ display }}</div>
</template>

<script>
export default {
  props: { teams: Array },
  methods: {
    gameLeaderDisplay() {
      const [team1, team2] = this.teams;
      let pluralPoints = true;

      if (
        team1.score !== team2.score &&
        Math.abs(team1.score - team2.score) === 1
      ) {
        pluralPoints = false;
      }

      if (team1.score === team2.score) {
        return "The teams are tied!";
      } else if (team1.score > team2.score) {
        return `${team1.name} is leading by ${team1.score - team2.score} point${
          pluralPoints ? "s" : ""
        }`;
      } else if (team2.score > team1.score) {
        return `${team2.name} is leading by ${team2.score - team1.score} point${
          pluralPoints ? "s" : ""
        }`;
      }
    },
  },
  computed: {
    display() {
      return this.gameLeaderDisplay();
    },
  },
};
</script>

<style>
</style>