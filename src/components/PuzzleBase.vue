<template>
  <div class="puzzle">
      <puzzle-card/>
      <h3>first card will be here</h3>
      <h3>and arrayed beneath it will be the options for the next step based on the rules</h3>
  </div>
</template>

<script>
import PuzzleCard from './PuzzleCard.vue'
export default {
  components: { PuzzleCard },
  name: 'PuzzleBase',
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
