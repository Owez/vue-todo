<template>
  <header class="header">
    <h1>Todo list</h1>
    <p>
      A small todo list by
      <a href="https://ogriffiths.com">me</a>.
    </p>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped>
.header {
  background-color: #38393d;

  text-align: center;
  padding-top: 1rem;
  padding-bottom: 1rem;
}

.header,
a {
  color: #ffffff;
}
</style>
