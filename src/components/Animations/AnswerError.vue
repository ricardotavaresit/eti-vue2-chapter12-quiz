<template>
  <div class="error">
    <h1>{{ title }}</h1>
    <button v-on:click="nextQuestion">Next question</button>
  </div>
</template>


<script>
export default {
  data() {
    return {
      title: "Error",
    };
  },
  methods: {
    nextQuestion() {
      this.$emit("changeMode");
    },
  },
};
</script>


<style scoped>
.error{
  border: 2px solid red;
  background-color: #dd95b3;
}
</style>