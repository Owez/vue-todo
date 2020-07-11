<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
    <AddTodo v-on:add-todo="addTodo" />
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";

export default {
  name: "App",
  components: {
    Header,
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "First fdgdfgdffgtodo",
          completed: false
        },
        {
          id: 2,
          title: "Other todo",
          completed: true
        }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.control {
  background-color: rgba(0, 0, 0, 0.05);
  width: 20%;
  height: 100%;
}
</style>
