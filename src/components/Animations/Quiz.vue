<template>
  <div class="container">
    <h2 v-text="title"></h2>
    <div class="row">
      <div class="custon-width">
        <transition name="effect" mode="out-in">
          <component :is="mode" v-on:changeMode="changeMode"></component>
        </transition>
      </div>
    </div>
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


<style scoped>
.effect-leave-active {
  animation: effect-out 2.5s;
}

.effect-enter-active {
  animation: effect-in 2.5s;
}

@keyframes effect-out {
  from {
    transform: rotateY(0deg);
  }
  to {
    transform: rotateY(90deg);
  }
}

@keyframes effect-in {
  from {
    transform: rotateY(90deg);
  }

  to {
    transform: rotateY(0deg);
  }
}

.custon-width{
  max-width: 700px; margin: 0 auto;
}
</style>
