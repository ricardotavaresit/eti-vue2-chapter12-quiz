<template>
  <div class="alert alert-success align-center">
    <h1>{{ title }}</h1>
    <button class="btn btn-success" v-on:click="nextQuestion">Next question</button>
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