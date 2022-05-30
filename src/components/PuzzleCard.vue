<template>
    <div class="card">
        <h2 class="card-text">{{string}}</h2>
        <div v-for="rule in rules" :key="rule.value">
      <button @click="handleClick(rule)">{{ruleLegend[rule -1]}}</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'puzzle-card',
    props: ['string','rules'],
    data(){
        return {
            ruleLegend: ["If you possess a string whose last letter is I, you may add a U to the end", 
            "Mx (x standing in for any sequence of characters following the M and running to the end of the string), you may add Mxx to your collection.",
            "If III occurs in the string, you may make a new string with U in place of III",
            "If UU occurs inside one of your strings, you can drop it"]
        }
    },
    methods: {
        handleClick(rule){
            if(rule == 3 ){
                let x = this.string.indexOf("III");
                this.$emit('rule', rule, x)
            }if (rule == 4 ){
                let x = this.string.indexOf("UU");
                this.$emit('rule', rule, x)
            }
            if(rule == 1 || rule == 2){
                this.$emit('rule', rule)
            }
            
        }
    }
}
</script>

<style>
.card {
    /* border: 2px solid rgba(162, 94, 73, 0.5); */
    width: 250px;
    height: auto;
    margin: auto;
    vertical-align: bottom;
    background-color: rgb(247, 178, 100);
	box-shadow:0 10px 10px 0 rgba(0,0,0,.24),0 17px 50px 0 rgba(0,0,0,.19);

}
.card-text {
    font-size: 1.5rem;
    color: rgba(0, 0, 0);
    text-align: center;
    vertical-align: bottom;
    margin: auto;
}
</style>