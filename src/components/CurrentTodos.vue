<template>
  <div id="current-todos" class="container">
    <h3 v-if="todos.length > 0">Активные задачи ({{todos.length}})</h3>
    <ul class="list-group">
      <li class="list-group-item" v-for="todo in todos" :key="todo.id">
        <span class="list-group-item-text">{{todo.body}}</span>
        <span class="list-group-item-time">Добавлено {{todo.date}}</span>
        <div class="btn-group">
          <button
            type="button"
            @click="edit(todo)"
            class="btn btn-edit"
            >
            Изменить
          </button>
          <button
            type="button"
            @click="complete(todo)"
            class="btn btn-complete"
            >
            Выполнено
          </button>
          <button
            type="button"
            @click="archive(todo)"
            class="btn btn-archive"
            :class="{archived: todo.archived}"
            :disabled="todo.archived"
            >
            В архив
          </button>
          <span :class="{archived: !todo.archived}" class="btn">В архиве</span>
          <button
            type="button"
            @click="remove(todo)"
            class="btn btn-remove"
            >
            &times;
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
