<template>
    <div class="box">
        <p>your reaction time was....</p> 
        <p class="result">{{ this.reactionTime }} ms</p>
        <p>That is <span :style="{color: chosenColor, fontSize: '40px'}">{{ this.rank }}</span></p>
    </div>
</template>

<script>
export default{
    name: 'Results',
    props: ['reactionTime'],
    data() {
        return {
            rank: null,
            chosenColor: null
        }
    },
    mounted(){
        if (this.reactionTime < 250){
            this.rank = 'Blazingly Fast'
            this.chosenColor = 'darkorange'
        } else if (this.reactionTime < 400){
            this.rank = 'Basically Average'
            this.chosenColor = 'darkgoldenrod'
        } else {
            this.rank = 'Beyond slow...'
            this.chosenColor = 'lightcoral'
        }
    }
}
</script>

<style>
    .result{
        font-size: 2em;
        color: #5DA399;
    }
    .box > *{
        margin: 100px 0;
    }
</style>

