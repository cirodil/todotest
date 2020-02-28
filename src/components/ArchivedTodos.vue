<template>
  <div id="completed-todos">
    <h3 v-if="archived.length > 0">Архивных({{archived.length}})</h3>
    <ul class="list-group">
        <li class="list-group-item" v-for="todo in archived" :key="todo.id">
            {{todo.body}}
            <button type="button" @click="remove(todo)" class="btn btn-default btn-sm">
            <span class="glyphicon glyphicon-remove-circle"></span> Remove
            </button>
            <button type="button" @click="archive(todo)" class="btn btn-default btn-sm">
            <span class="glyphicon glyphicon-remove-circle"></span> Убрать из архива
            </button>
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
