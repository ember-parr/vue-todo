/* eslint-disable */

<template>
  <div :class="{ completed: todo.complete }">
    <h3>{{ todo.name }}</h3>
    <button @click="handleClick" >
      {{ taskStatus }}
    </button>
  </div>
</template>

<script>
export default {
  props: ["todo"],
  methods: {
    handleClick() {
      this.$emit("status-change", this.todo);
    }
  },
  computed: {
    taskStatus() {
      return this.todo.complete ? "Mark Incomplete" : "Done!";
    }
  }
};
</script>

<style scoped>
div {
  margin: 15px;
  padding: 10px;
  border: 3px solid teal;
  width: 90%;
  background: white;
}

button {
  padding: 10px;
  margin-bottom: 20px;
  color: white;
  border-radius: 12px;
  background-color: teal;
  border: teal;
}

.completed {
  background-color: lightgray;
  border: darkgray;
}

.completed button {
    background-color: darkgray;
}
</style>
