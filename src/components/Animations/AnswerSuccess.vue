<template>
  <div class="success">
    <h1>{{ title }}</h1>
    <button v-on:click="nextQuestion">Next question</button>
  </div>
</template>


<script>
export default {
  data() {
    return {
      title: "Success",
    };
  },
  methods:{
    nextQuestion(){
      this.$emit("changeMode")
    }
  }
};
</script>
<style scoped>
.success{
  border: 2px solid green;
  background-color: #72d196;
}
</style>