<script>
import Block from '@/components/Block'
export default {
  name: 'App',
  components: {
    Block
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
    }
  }
}
</script>

<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @catchReaction="endGame"/>
  <p>Reaction time:{{ score }}ms</p>
</template>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>