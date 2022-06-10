<template>
  <div id="app">
    <h1 v-text="msg"></h1>
    <app-quiz />
    <hr />
    <button class="bt-show" v-on:click.prevent="show = !show">Show</button>
    <transition>
      <div class="presentation-area" v-if="show">Present...</div>
    </transition>
  </div>
</template>

<script>
import Quiz from "./components/Animations/Quiz";

export default {
  name: "app",
  data() {
    return {
      msg: "Component App",
      show: false,
    };
  },
  components: {
    "app-quiz": Quiz,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.presentation-area {
  background-color: #cccc;
  margin: 10px;
  padding: 20px;
}

.bt-show {
  margin-top: 20px;
}
</style>
