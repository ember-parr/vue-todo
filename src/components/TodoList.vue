/* eslint-disable */
<template>
  <div>
    <h2>You have {{ itemsRemaining.length }} tasks left for today</h2>
    <div v-for="item in sortedTasks" :key="item.id" class="todoList">
      <todo-item :todo="item" @status-change="handleStatusChange" />
    </div>
  </div>
</template>

<script>
import { todoItems } from "../data";
import TodoItem from "./TodoItem.vue";
import _ from "lodash";
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
      return this.todos.filter(t => !t.complete);
    },
    sortedTasks() {
      return _.orderBy(this.todos, 'complete')
    }
  }
};
</script>

<style scoped>
.todoList {
  display: inline-flex;
  justify-content: space-evenly;
  align-content: flex-start;
}
h2 {
  color: teal;
  opacity: 0.75;
}
</style>
