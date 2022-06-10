<template>
  <div>
    <h2 v-text="title"></h2>
    <component :is="mode" v-on:changeMode="changeMode"></component>
  </div>
</template>

<script>
import Question from "./Question";
import AnswerError from "./AnswerError";
import AnswerSuccess from "./AnswerSuccess";
export default {
  data() {
    return {
      title: "Component Quiz",
      mode: "app-question",
    };
  },
  components: {
    "app-question": Question,
    AnswerError,
    AnswerSuccess,
  },
  methods: {
    changeMode(mode) {
      if (mode == undefined) {
        this.mode = "app-question";
      } else {
        this.mode = mode;
      }
    },
  },
};
</script>

