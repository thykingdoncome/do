<template>
  <div>
    <form @submit.prevent="addTodo">
      <input type="text" name="title" v-model="title" placeholder="Add todo..." />
      <input type="submit" value="Add" class="btn" />
    </form>
  </div>
</template>

<script>
// import { v4 as uuidv4 } from "uuid";

export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
      newTodo: {}
    };
  },
  methods: {
    addTodo() {
      this.newTodo = {
        // id: uuidv4(),
        title: this.title,
        completed: false,
      };

      this.$emit("add-todo", this.newTodo);
      this.title = ''
    },
  },
};
</script>

<style>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}
input[type="submit"] {
  flex: 2;
}
</style>
