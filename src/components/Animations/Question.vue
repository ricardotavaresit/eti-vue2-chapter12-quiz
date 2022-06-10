<template>
  <div class="card">
    <div class="card-header">
      <h2 v-text="question"></h2>
    </div>
    <div class="card-body">
      <form class="form form-inline" v-on:submit.prevent="checkResult">
        <input class="form-control" type="text" placeholder="Awswer" v-model="reply" />
        <button class="btn btn-primary" type="submit">Awswer</button>
      </form>
    </div>
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
      let mode = "answerError";
      if (this.reply == this.result) {
        mode = "answerSuccess";
      }
      this.$emit("changeMode", mode);
    },
  },
};
</script>

<style scoped>
.defaul {
  border: 2px solid blue;
  background-color: #6f95dd;
}
</style>

