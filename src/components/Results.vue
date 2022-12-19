<template>
    <div>
        <p>your reaction time was....</p> 
        <p class="result">{{ this.reactionTime }} ms</p>
    </div>
</template>

<script>
export default{
    name: 'Results',
    props: ['reactionTime'],
}
</script>

<style>
    .result{
        font-size: 2em;
        color: #5DA399;
    }
</style>

