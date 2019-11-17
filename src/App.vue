<template>
  <div id="app">
    <Header />
    <AddTodo />
    <Todos v-bind:newTodo="todos" v-on:delete-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";
import Header from "./components/Header";

export default {
  name: "app",
  components: {
    Todos,
    AddTodo,
    Header
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Project 1",
          completed: false
        },
        {
          id: 2,
          title: "Project 2",
          completed: false
        }
      ]
    };
  },

  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(item => item.id !== id);
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
