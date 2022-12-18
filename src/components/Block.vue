<template>
    <div class="block" @click="clicked" v-if="showBlock">
        Click me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data(){
        return {
            showBlock: false,
        }
    },
    methods: {
        clicked(){

        }
    },
    mounted(){
        console.log(this.delay)
        setTimeout(() => {
            this.showBlock = true
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
        margin: 40px auto;
    }
</style>
