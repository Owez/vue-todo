<template>
  <div>
    <div class="todo-mockup">
      <form @submit="addTodo">
        <input type="text" v-model="title" name="title" id="title" placeholder="Todo" />
        <input type="submit" class="control" id="add-btn" value="Add" />
      </form>
    </div>
    <div class="add-todo-spacer"></div>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        id: uuidv4(),
        title: this.title,
        completed: false
      };

      this.$emit("add-todo", newTodo);
    }
  }
};
</script>

<style scoped>
.add-todo-spacer {
  margin-top: 1rem;
}

#title {
  border: 0;
  background: transparent;
  font-size: large;
  font-weight: bold;
  height: 100%;
  width: calc(80% - 0.15rem);
}

#add-btn {
  border: 0;
  margin: 0;
  font-size: large;
  height: 3rem;
  color: black;
}

.todo-mockup {
  background-color: #f3f3f3;
  border-bottom: 1px solid #dadada;
  padding-left: 0.75rem;
  height: 3rem;
}
</style>