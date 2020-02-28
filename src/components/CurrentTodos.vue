<template>
  <div id="current-todos" class="container">
    <h3 v-if="todos.length > 0">Активные задачи ({{todos.length}})</h3>
    <ul class="list-group">
      <li class="list-group-item" v-for="todo in todos" :key="todo.id">
        <span class="list-group-item-text">{{todo.body}}</span>
        <span class="list-group-item-time">{{todo.date.toLocaleString()}}</span>
        <span :class="{archived: !todo.archived}">В архиве</span>
      <div class="btn-group">
        <button type="button" @click="edit(todo)" class="btn btn-edit">
        <span class="glyphicon glyphicon-edit"></span> Изменить
        </button>
        <button type="button" @click="complete(todo)" class="btn btn-complete">
        <span class="glyphicon glyphicon-ok-circle"></span> Выполнено
        </button>
        <button type="button" @click="archive(todo)" class="btn btn-archive" :class="{archived: todo.archived}" :disabled="todo.archived">
        <span class="glyphicon glyphicon-ok-circle"></span> В архив
        </button>
        <button type="button" @click="remove(todo)" class="btn btn-remove">
        <span class="glyphicon glyphicon-remove-circle"></span> &times;
        </button>
      </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  methods: {
    edit (todo) {
      this.$store.dispatch('editTodo', todo)
    },
    complete (todo) {
      this.$store.dispatch('completeTodo', todo)
    },
    archive (todo) {
      this.$store.dispatch('archiveTodo', todo)
    },
    remove (todo) {
      this.$store.dispatch('removeTodo', todo)
    }
  },
  computed: {
    todos () {
      return this.$store.getters.todos
    }
  }
}
</script>
<style>

  .list-group {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }
  .list-group-item {
    width: 75%;
    border: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    padding: .5rem 1rem;
    margin-bottom: 1rem;
  }

  .list-group-item-text {
    font-style: italic;
  }

  .btn {
    margin-right: 1rem;
  }
  .btn-remove {
    border-radius: 50%;
    border: none;
    color: #fff;
    background: red;
  }

  .archived {
    display: none;
  }

</style>
