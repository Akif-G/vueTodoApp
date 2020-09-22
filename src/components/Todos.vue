<template>
  <div class="alltodo">
    <!-- use v-bind:key for looping thro-->
    <div v-for="todo in todos" v-bind:key="todo.id">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo',todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "Todos",
  components: {
    TodoItem,
  },
  props: ["todos"],
};
</script>

<style scoped>
.alltodo {
  margin: 10px;
  display: grid;
  grid-template-columns: [c1] 1fr [c3] 1fr [c4] 1fr [c5];
  grid-template-rows: [r1] 100px [r2] 100px [r3];
  grid-column-gap: 10px;
  grid-row-gap: 10px;
  padding: 10px;
}
</style>