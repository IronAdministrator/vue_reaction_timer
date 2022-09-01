<script>
  export default {
    props: ['score'],
    data() {
      return {
        rank: null,
      }
    },
    mounted () {
      this.score < 250 ? this.rank = 'Ninja Fingers' :
      this.score < 400 ? this.rank = 'Rapid Fingers' :
      this.rank = 'You need some training'
    },
  }
</script>

<template>
  <h3>Reaction time: {{ score }} ms</h3>
  <h2 class="rank">{{rank}}</h2>
</template>

<style scoped>
  .rank {
    font-size: 1.4em;
    color: #0faf87;
    font-weight: bold;
  }
</style>