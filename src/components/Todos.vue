<template>
  <div>
    <div v-for="todo in todos" :key="todo.id">
      <!-- {{ todo.title }} -->
      <TodoItem :todo="todo" @del-todo="$emit('del-todo', todo.id)"/>
      <!-- <TodoItem :todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/> -->
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"]
};
</script>

<style scoped></style>
