<template>
    <div class="block" @click="stopTimer" v-if="showBlock">
        Click me
    </div>
</template>

<script>
export default {
    name: 'Block',
    props: ['delay'],
    data(){
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            },10)
        },
        stopTimer() {
            clearInterval(this.timer)
            this.$emit('stop',this.reactionTime)
            console.log(this.reactionTime + "ms")
        }
    },
    mounted(){
        console.log(this.delay)
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        }, this.delay)
    }
}
</script>

<style>
    .block {
        width: 400px;
        border-radius: 20px;
        background: #5DA399;
        color: white;
        text-align: center;
        padding: 100px 0;
        margin: 100px auto;
        cursor: pointer;
    }
</style>
