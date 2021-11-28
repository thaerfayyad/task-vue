<template>
  <div class="todo-item" v-bind:class="{ 'is-complete': !todo.completed }">
    <p>
      <input type="checkbox" v-on:change="markComplete" />
      {{ todo.title }}
      <button class="del" @click="$emit('del-todo',todo.id)">x</button>
    </p>
  </div>
</template>
<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>
<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px;
}
.is-complete {
  text-decoration: line-through;
}
.del {
  background: red;
}
</style>
>
