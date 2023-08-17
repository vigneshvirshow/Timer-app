<template>
<div id="app">
  <h1 style="color: black;text-decoration:underline;">Timer</h1>
  <button v-on:click="startTimer">Start timer</button>
  <h1 style="color: aquamarine;">Time: {{ time }}</h1>
  <h2 v-if="time >= 5 && time < 6" style="color:blue">The timer will end in 5 seconds</h2>
  <h2 v-if="time >= 9 && time < 10" style="color:#ffbf00">The timer will end in 1 second</h2>
  <h2 v-if=" time == 10" style="color:red">The time is up!</h2>
  </div>
  </template>
  <script>
export default {
  name: 'App',
  data() {
    return {
      time: 0,
      timerId: null,
    };
  },
  methods: {
    startTimer() {
      this.timerId = setInterval(() => {
        this.time++;
        if (this.time >= 10) {
          this.stopTimer();
        }
      }, 1000);
    },
    stopTimer() {
      clearInterval(this.timerId);
      this.timerId = null;
    },
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>