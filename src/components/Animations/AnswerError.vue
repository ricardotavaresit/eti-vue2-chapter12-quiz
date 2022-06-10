<template>
  <div class="alert alert-danger text-center">
    <h1>{{ title }}</h1>
    <button class="btn btn-danger" v-on:click="nextQuestion">Next question</button>
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