<template>
  <div id="app">
    <MatchupTitle :teams="teams" />
    <GameStatus :teams="teams" />
    <ScoreCard
      :score="teams[0].score"
      @pointUp="updateScore(teams[0], 1)"
      @pointDown="updateScore(teams[0], -1)"
    />
    <ScoreCard
      :score="teams[1].score"
      @pointUp="updateScore(teams[1], 1)"
      @pointDown="updateScore(teams[1], -1)"
    />
  </div>
</template>

<script>
import MatchupTitle from "./components/MatchupTitle";
import ScoreCard from "./components/ScoreCard";
import GameStatus from "./components/GameStatus";

export default {
  components: {
    MatchupTitle,
    ScoreCard,
    GameStatus,
  },
  data() {
    return {
      teams: [
        {
          name: "Team 1",
          score: 0,
        },
        {
          name: "Team 2",
          score: 0,
        },
      ],
    };
  },
  methods: {
    updateScore(team, points) {
      const newScore = team.score + points;

      if (newScore >= 0) {
        team.score = newScore;
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
