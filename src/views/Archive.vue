<template>
  <div class="archive">
    <div id="nav">
      <hr>
      <h1>Архивные задачи</h1>
      <hr>
      <router-link to="/">Главная</router-link> |
      <router-link to="/archive">Архивные</router-link>
    </div>
    <ArchivedTodos />
  </div>
</template>

<script>
import ArchivedTodos from '../components/ArchivedTodos'
export default {
  components: {
    ArchivedTodos
  }
}
</script>

<style lang="scss">
#archive {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
