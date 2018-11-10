<template>
  <div>
    <div class="list-info">
      <p>Completed Tasks: {{ todos.filter(todo => { return todo.done === true }).length }}</p>
      <p>Pending Tasks: {{ todos.filter(todo => { return todo.done === false }).length }}</p>
    </div>
    <TodoItem
      v-on:delete-todo="deleteTodo" 
      v-on:complete-todo="completeTodo" 
      v-for="(todo,index) in todos" 
      v-bind:todo="todo" 
      v-bind:key="index"
    />
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  props: ["todos"],
  components: {
    TodoItem
  },
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    completeTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    }
  }
};
</script>

<style lang="scss" scoped>
.list-info {
  margin: 2rem;
  text-align: center;
}
</style>
