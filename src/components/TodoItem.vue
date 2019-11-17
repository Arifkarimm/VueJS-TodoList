<template>
  <div>
    <div class="todo-item" v-bind:class="{'is-complete': moveTodo.completed}">
      <p>
        <input type="checkbox" v-on:change="markCompleted" />
        {{moveTodo.title}}
        <button
          @click="$emit('delete-todo', moveTodo.id)"
          class="del"
        >Delete</button>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["moveTodo"],
  methods: {
    markCompleted() {
      this.moveTodo.completed = !this.moveTodo.completed;
    }
  }
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: #000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 5px;
  cursor: pointer;
  float: right;
}
</style>