<template>
  <div class="con">
    <h3>you may view the user here</h3>
    <p>User Name: {{ switchName() }}</p>
    <p>User Name: {{ myName }}</p>
    <p>Age: {{ userAge }}</p>
    <button @click="resetName">reset</button>
    <button @click="resetFn()">resetfun</button>
  </div>
</template>
<script>
import { eventBus } from "../main";

export default {
  props: {
    myName: {
      type: String
    },
    resetFn: Function,
    userAge: Number
  },
  methods: {
    switchName() {
      return this.myName
        .split("")
        .reverse()
        .join("");
    },
    resetName() {
      this.myName = "max";
      this.$emit("nameWasReset", this.myName);
    }
  },
  created() {
    eventBus.$on("ageEdit", age => {
      this.userAge = age;
    });
  }
};
</script>
<style scoped>
div {
  background-color: aqua;
}
</style>
