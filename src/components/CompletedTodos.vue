<template>
  <div id="completed-todos">
    <h3 v-if="completed.length > 0">Выполнено ({{completed.length}})</h3>
    <ul class="list-group">
        <li class="list-group-item" v-for="todo in completed" :key="todo.id">
          <span class="list-group-item-text">{{todo.body}}</span>
          <div class="btn-group">
            <button type="button" @click="remove(todo)" class="btn btn-remove">
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
    }
  },
  computed: {
    completed () {
      return this.$store.getters.completedTodos
    }
  }
}
</script>
