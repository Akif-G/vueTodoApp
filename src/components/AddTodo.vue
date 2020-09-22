<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Add Todo!" />
      <input type="submit" value="Submit" class="btn" />
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
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false,
      };
      this.$emit("add-todo", newTodo);
      this.title = "";
    },
  },
};
</script>

<style scoped>
form {
  margin: 5px;
  display: flex;
  padding: 5px;
}
input[type="text"] {
  font-size: 120%;
  flex: 5;
  padding: 10px;
  background-color: #03dac6;
  border: none;
}

input[type="submit"] {
  font-size: 150%;
  background-color: #018786;
  flex: 2;
  padding: 10px;
  margin-left: 5px;
}
input:hover {
  opacity: 0.9;
}

input[type="submit"]:hover {
  transform: scale(0.95);
  transition: 0.2s ease-in-out;
}
</style>