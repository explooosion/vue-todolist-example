<template>
  <div>
    <TodoList v-bind:todos="todos" />
    <!-- <CreateTodo v-on:add-todo="addTodo" /> -->
    <CreateTodo v-on:create-todo="addTodo" />
  </div>
</template>

<script>
import TodoList from "./components/TodoList";
import CreateTodo from "./components/CreateTodo.vue";

export default {
  name: "app",
  components: {
    TodoList,
    CreateTodo
  },
  data() {
    return {
      todos: [
        {
          title: "Todo A",
          project: "Project A",
          done: false
        },
        {
          title: "Todo B",
          project: "Project B",
          done: true
        },
        {
          title: "Todo C",
          project: "Project C",
          done: false
        },
        {
          title: "Todo D",
          project: "Project D",
          done: false
        }
      ]
    };
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
