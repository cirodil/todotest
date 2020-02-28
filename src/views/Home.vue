<template>
  <div class="home">
    <div id="nav">
      <hr>
      <h1>Список задач</h1>
      <hr>
      <router-link to="/">Главная</router-link> |
      <router-link to="/archive">Архивные</router-link>
    </div>
    <CompletedTodos></CompletedTodos>
    <GetTodo></GetTodo>
    <CurrentTodos></CurrentTodos>
  </div>
</template>

<script>
import GetTodo from '../components/GetTodo.vue'
import CurrentTodos from '../components/CurrentTodos.vue'
import CompletedTodos from '../components/CompletedTodos.vue'
export default {
  components: {
    GetTodo,
    CurrentTodos,
    CompletedTodos
  }
}
</script>
