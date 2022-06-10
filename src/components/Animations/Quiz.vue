<template>
  <div>
    <h2 v-text="title"></h2>
    <component :is="mode" v-on:changeMode="changeMode"></component>
  </div>
</template>

<script>
import Question from "./Question";
export default {
  data() {
    return {
      title: "Component Quiz",
      mode: "app-question",
    };
  },
  components: {
    "app-question": Question,
  },
  methods: {
    changeMode() {
      alert("changeMode");
    },
  },
};
</script>
