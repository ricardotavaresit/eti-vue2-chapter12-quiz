<template>
  <div>
    <h2 v-text="title"></h2>
    <app-question />
  </div>
</template>

<script>
import Question from "./Question.vue";
export default {
  data() {
    return {
      title: "Component Quiz",
    };
  },
  components: {
    "app-question": Question,
  },
};
</script>


<style scoped>
</style>