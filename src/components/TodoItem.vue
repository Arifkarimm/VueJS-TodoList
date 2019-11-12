<template>
  <div>
    <div>
      <p>{{moveTodo.title}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["moveTodo"]
};
</script>

<style lang="scss" scoped>
</style>