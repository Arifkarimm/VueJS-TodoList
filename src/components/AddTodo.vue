<template>
  <div>
    <form @submit="AddTodo">
      <input type="text" title="name" v-model="title" placeholder="Add Todo...." />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    AddTodo(e) {
      e.preventDefault();
      const newTodo = {
        id: Date.now(),
        title: this.title,
        completed: false
      };

      // send data to App.vue js
      this.$emit("add-todo", newTodo);
      this.title = "";
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
  width: 600px;
  margin: 0 auto;
}

input[type="text"] {
  flex: 10;
  padding: 5px;
}

input[type="submit"] {
  flex: 2;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
</style>