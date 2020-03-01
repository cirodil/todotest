<template>
  <div id="completed-todos">
    <h3 v-if="archived.length > 0">Архивных({{archived.length}})</h3>
    <ul class="list-group">
      <li class="list-group-item" v-for="todo in archived" :key="todo.id">
        <span class="list-group-item-text">{{todo.body}}</span>
        <span class="list-group-item-time">{{todo.date.toLocaleString()}}</span>
        <div class="btn-group">
          <button
            type="button"
            @click="archive(todo)"
            class="btn btn-default"
          >
            Убрать из архива
          </button>
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
    remove (todo) {
      this.$store.dispatch('removeTodo', todo)
    },
    archive (todo) {
      this.$store.dispatch('archiveTodo', todo)
    }
  },
  computed: {
    archived () {
      return this.$store.getters.archivedTodos
    }
  }
}
</script>
