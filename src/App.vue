<template>
  <div id="app" >
    <h1>Let's Get Things Done</h1>
    <img className="headerImg" alt="checkmark" src="./assets/check-favicon.png" />
    <todo-list />
  </div>
</template>

<script>
import TodoList from "./components/TodoList";

export default {
  name: "App",
  components: {
    TodoList
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-image: url(assets/background.jpg);
  background-repeat: repeat-y;
}

#app img {
  width: 150px;
  height: auto;
}
#app h1 {
  padding-top: 50px;
}
</style>
