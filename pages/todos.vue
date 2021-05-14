<template>
  <div>
    <h1>Todos</h1>
    <div>
      <input @keyup.enter="addTodo" type="text" />
      <b-button @click="remove" variant="danger">删除</b-button>
    </div>
    <ol>
      <li v-for="todo in list" :key="todo.text">
        <label>
          <input :checked="todo.done" @change="toggle(todo)" type="checkbox" />
          <span :class="{ done: todo.done }">{{ todo.text }}</span>
        </label>
      </li>
    </ol>
  </div>
</template>
<script>
import { mapState } from "vuex";
import { mapMutations } from "vuex";
export default {
  computed: {
    ...mapState({
      list: (state) => state.todos.list,
    }),
  },
  methods: {
    addTodo(e) {
      this.add(e.target.value);
      e.target.value = "";
    },
    // 映射store.mutations
    ...mapMutations({
      add: "todos/add",
      remove: "todos/remove",
      toggle: "todos/toggle",
    }),
  },
};
</script>
<style scoped>
.done {
  text-decoration: line-through;
}
</style>