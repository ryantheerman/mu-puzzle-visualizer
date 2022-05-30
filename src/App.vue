<template>
  <h2>MU Puzzle Visualizer</h2>
  <h3>Introduction</h3>
  <h3>Rules and Directions</h3>
  <puzzle-base/>
</template>

<script>
import PuzzleBase from './components/PuzzleBase.vue'

export default {
  name: 'App',
  components: {
    PuzzleBase
  }
}
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
