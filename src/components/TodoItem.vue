<template>
  <div class="todo-item" :class="{ 'is-complete': todo.completed }">
    <h3>
      <input type="checkbox" @change="markComplete" />
      {{ todo.title }}
      <button class="del" @click="$emit('del-todo', todo.id)">x</button>
    </h3>
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
  border-bottom: 1px #ccc dotted;
}
.is-complete {
  text-decoration: line-through;
}
.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
  outline: 0;
}
</style>
