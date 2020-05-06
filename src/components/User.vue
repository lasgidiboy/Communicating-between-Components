<template>
  <div class="component">
    <div class="container">
      <h1>The user component</h1>
      <button @click="changeName">change name</button>
      <p>name is {{ name }}</p>
      <p>age is {{ age }}</p>
      <div class="row">
        <div class=" col-xs-6 col-md-6 col-sm-6">
          <UserEdit :userAge="age" @ageEdit="age=$event" :myName="name"></UserEdit>
        </div>
        <div class=" col-xs-6 col-md-6 col-sm-6">
          <app-server-details
            :myName="name"
            @nameWasReset="name = $event"
            :resetFn="resetName"
            :userAge="age"
          ></app-server-details>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import UserDetail from "./UserDetail.vue";
import UserEdit from "./UserEdit.vue";
export default {
  data() {
    return {
      name: "max",
      age: 27
    };
  },
  methods: {
    changeName() {
      this.name = "papper";
    },
    resetName() {
      this.name = "Max";
    }
  },
  components: {
    UserEdit,
    "app-server-details": UserDetail
  }
};
</script>
<style scoped>
.component {
  background-color: lightblue;
  border: 2px solid black;
  padding: 25px;
}
</style>
