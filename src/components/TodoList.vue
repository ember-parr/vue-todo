<template>
  <div>
    <h2>You have {{ itemsRemaining.length }} tasks left for today</h2>
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
  },
  methods: {
      handleStatusChange(item) {
          item.complete = !item.complete;
          console.log(item);
      }
  },
  computed: {
      itemsRemaining() {
          return this.todos.filter(t => !t.complete)
      }
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
