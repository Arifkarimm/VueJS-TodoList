<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in newTodo">
      <TodoItem v-bind:moveTodo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";
export default {
  name: "Todos",
  props: ["newTodo"],
  components: {
    TodoItem
  }
};
</script>

<style scoped>
</style>