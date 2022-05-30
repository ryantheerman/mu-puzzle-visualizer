<template>
  <div class="puzzle">
      <h3>first card will be here</h3>
      <puzzle-card :string="currentString" :rules="rulesOptions" @rule="enactRule" />
      <h3>and arrayed beneath it will be the options for the next step based on the rules</h3>
  </div>
</template>

<script>
import PuzzleCard from './PuzzleCard.vue'
export default {
  components: { PuzzleCard },
  name: 'PuzzleBase',
  props: {
    
  },
  data() {
    return {
      currentString: "MI",
      location: 0,
      rulesWritten: {first: "If you possess a string whose last letter is I, you may add a U to the end",
              second: "Mx (x standing in for any sequence of characters following the M and running to the end of the string), you may add Mxx to your collection.",
              third: "If III occurs in the string, you may make a new string with U in place of III",
              fourth: "If UU occurs inside one of your strings, you can drop it"},
      rulesLogic: {first: () => {
      this.currentString += "U"},
      second: () => {
      this.currentString += this.currentString.substring(1, this.currentString.length);},
      third: () => {
      this.currentString = this.currentString.substring(0, this.location ) + "U" + this.currentString.substring(this.location + 3, this.currentString.length)},
      fourth: () => {
      this.currentString = this.currentString.substring(0, this.location ) + this.currentString.substring(this.location + 2, this.currentString.length)}},
      rulesOptions: [],
    }
  },
  methods: {
      whichRulesAreValid(){
        this.rulesOptions = []
        if(this.currentString.substring(this.currentString.length - 1, this.currentString.length) == "I"){
          this.rulesOptions.push(1)
        }
        if(this.currentString.length > 1 && this.currentString.substring(0,1) == "M"){
          this.rulesOptions.push(2)
        }
        if(this.currentString.includes("III")){
          this.iLocation = this.currentString.indexOf("III");
          this.rulesOptions.unshift(3)
        }
        if(this.currentString.includes("UU")){
          this.uLocation = this.currentString.indexOf("UU");
          this.rulesOptions.unshift(4)
        }
      },
      enactRule(...args){
        let rule = args[0];
        if(args[1] != undefined){
          this.location = args[1];
        }
        if(rule == 1){
          this.rulesLogic.first()
        }
        if(rule == 2){
          this.rulesLogic.second()
        }
        if(rule == 3){
          this.rulesLogic.third()
        }
        if(rule == 4){
          this.rulesLogic.fourth()
        }
        this.whichRulesAreValid();
      }
  },
  created() {
    this.whichRulesAreValid();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
