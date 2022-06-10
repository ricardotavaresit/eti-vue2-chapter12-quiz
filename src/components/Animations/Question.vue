<template>
  <div>
    <h2 v-text="question"></h2>
    <form v-on:submit.prevent="checkResult">
      <input type="text" placeholder="Awswer" v-model="reply" />
      <button type="submit">Awswer</button>
    </form>
  </div>
</template>


<script>
export default {
  data() {
    return {
      title: "Question Component",
      question: "Generate question....",
      result: 0,
      reply: "",
    };
  },
  created() {
    this.generateQuestion();
  },
  methods: {
    generateQuestion() {
      let numberOne = this.generateRandonNumber(1, 100);
      let numberTwo = this.generateRandonNumber(1, 100);

      this.result = numberOne + numberTwo;

      this.question = `What is th sum of ${numberOne} and ${numberTwo}`;
    },
    generateRandonNumber(min, max) {
      return Math.round(Math.random() * max) + min;
    },
    checkResult() {
      if (this.reply == this.result) {
        alert("Correct!");
      } else {
        alert("Wrong");
      }
      this.$emit("changeMode");
    },
  },
};
</script>