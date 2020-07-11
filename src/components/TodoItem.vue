<template>
  <div class="todo-item">
    <h3 class="todo-text" v-bind:class="{'line-through':todo.completed}">
      {{ todo.title }}
      <span class="id-text">#{{ todo.id }}</span>
    </h3>
    <div class="control control-toggles">
      <button
        class="status"
        v-bind:class="{'green-bg':todo.completed, 'red-bg':!todo.completed}"
        v-on:click="markComplete"
      ></button>
      <button class="delete" @click="$emit('del-todo', todo.id)">x</button>
    </div>
    <div class="clear-float"></div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.id-text {
  color: #aaaaaa;
}

.todo-item {
  background-color: #f3f3f3;
  border-bottom: 1px solid #dadada;
}

.todo-text {
  padding: 0.5rem;
  width: 80%;
  float: left;
  overflow: hidden;
  white-space: nowrap;
}

.green-bg {
  background-color: rgb(100, 200, 89);
}

.red-bg {
  background-color: rgb(200, 100, 89);
}

.control-toggles {
  height: 3rem;
  float: right;
  display: flex;
  justify-content: center;
  align-items: center;
}

.status {
  border: 0;
  width: 40%;
  height: 1.5rem;
  border-radius: 0.75rem;
  margin-right: 0.5rem;
}

.delete {
  height: 1.5rem;
  width: 1.5rem;
  color: black;
  border: 1px solid black;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  background-color: transparent;
}

.line-through {
  text-decoration: line-through;
}

.clear-float {
  clear: both;
}
</style>