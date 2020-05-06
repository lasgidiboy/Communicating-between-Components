<template>
  <div class="con">
    <h3>you may edit the user here</h3>
    <p>user Age: {{ userAge }}</p>
    <p>user Name: {{ myName }}</p>
    <button @click="editAge">edit</button>
  </div>
</template>
<script>
import { eventBus } from "../main";
export default {
  props: ["userAge", "myName"],
  methods: {
    editAge() {
      this.userAge = 30;
      // this.$emit('ageEdit', this.userAge)
      eventBus.$emit("ageEdit", this.userAge);
    }
  }
};
</script>
<style scoped>
div {
  background-color: brown;
}
</style>
