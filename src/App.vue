<template>
  <div>
    <header>
      <h1>Trello Like App</h1>
    </header>
    <Todo></Todo>
  </div>
</template>

<script>
import Todo from "./components/Todo.vue";
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

export default {
  name: "app",
  components: {
    Todo
  }
};
</script>

<style>
h1 {
  height: 50px;
  color: white;
  font-family: "Indie Flower", cursive;
  text-align: center;
  width: 100vw;
}

body {
  background-image: url("./assets/background.jpg");
  background-size: cover;
  width: 100vw;
  height: 100vh;
}
</style>
