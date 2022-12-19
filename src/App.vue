<template>
  <h1>Epic Reaction Timer</h1>
  <button class="button" :class="{ buttonPlay: isPlaying }" @click="start" :disabled="isPlaying">{{ this.playText }}</button>
  <Block v-if="isPlaying" :delay="this.delay" @stop="stopGame"/>
  <Results v-if="showResults" :reactionTime="this.reactionTime"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: {
    Block,
    Results
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      showResults: false,
      reactionTime: 0,
      playText: "play",
    }
  },
  methods: {
    start() {
      this.showResults = false
      this.playText = "play"
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    },
    stopGame(reactionTime) {
      this.isPlaying = false
      this.playText = "play again?"
      this.reactionTime = reactionTime
      this.showResults = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  font-size: x-large;
  margin-top: 60px;
}
.button{
  width: 100px;
  border-radius: 10px;
  border-color: #5DA399;
  background: #5DA399;
  color: white;
  text-align: center;
  padding: 10px 0;
  margin: 20px auto;
}

.buttonPlay{
  background: #355b56;
}
</style>
