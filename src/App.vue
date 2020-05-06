<template>
  <div class="container">
    <User></User>
  </div>
</template>

<script>
import User from "./components/User.vue";
export default {
  components: {
    User
  }
};
</script>

<style>
.con{
  border: 2px solid black;
  padding: 25px;
  margin-top: 20px;
}
</style>
