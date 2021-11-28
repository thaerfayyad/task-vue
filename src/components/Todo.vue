<template>
  <div>
    <div>
      <div v-for="todo in todos" :key="todo.id">
        <!-- <h3>{{ todo.title }} {{'the key is : '+ todo.id }}</h3> -->
        <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo',todo.id)" />
        <h4></h4>
      </div>
    </div>
  </div>
</template> 

<script>
import TodoItem from '@/components/TodoItem';
export default {
  name: "Todos",
  components: {
      TodoItem
  },
  props: ["todos"],
};
</script>
<style scoped></style>
