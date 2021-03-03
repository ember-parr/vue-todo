<template>
  <div>
    <h2>You have XXXX tasks left for today</h2>
    <div v-for="item in todos" :key="item.id" class="todoList">
      <todo-item :todo="item" @status-change="handleStatusChange" />
    </div>
  </div>
</template>

<script>
import { todoItems } from "../data";
import TodoItem from "./TodoItem.vue";
export default {
  components: { TodoItem },
  data() {
    return {
      todos: [...todoItems]
    };
  }
};
</script>

<style scoped>
.todoList {
  display: flex;
  justify-content: space-evenly;
}
h2 {
  color: teal;
}
</style>
