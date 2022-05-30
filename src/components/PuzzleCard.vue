<template>
    <div class="card">
        <h2 class="card-text">MI</h2>
    </div>
</template>

<script>
export default {
    name: 'puzzle-card'
}
</script>

<style>
.card {
    /* border: 2px solid rgba(162, 94, 73, 0.5); */
    width: 200px;
    height: 50px;
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