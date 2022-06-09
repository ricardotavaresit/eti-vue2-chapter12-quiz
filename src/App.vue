<template>
  <div id="app">
    <h1 v-text="msg"></h1>
    <app-quiz />
  </div>
</template>

<script>
import Quiz from "./components/Animations/Quiz";

export default {
  name: "app",
  data() {
    return {
      msg: "Component App",
    };
  },
  components: {
    'app-quiz': Quiz
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

</style>
