<template>
  <div class="todo-list">
    <h1 style="margin-top: 30px; text-align: center;">Vue ToDo List</h1>
    <div class="todo-box">
      <div class="todo-header">
        <div class="task-count">Tasks<span class="count">{{ todos.length }}</span></div>
        <div class="task-done" v-if="doneCount > 0">Tasks Done<span class="count">{{ doneCount }}</span></div>
        <button class="task-delete" v-if="doneCount > 0" @click="deleteDone"><i class="fas fa-trash"></i> Task Done</button>
        <button class="task-delete-all" @click="deleteAll"><i class="fas fa-trash"></i> Tasks</button>
      </div>
      <div class="todo-items" v-for="(todo, index) in todos" :key="index">
        <TodoItem :todo="todo" />
      </div>
      <div class="add-task">
        <input type="text" v-model="newTodo" @keyup.enter="addTodo">
        <button @click="addTodo" class="add-button">+</button>
      </div>
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItems.vue'

export default {
  components: { TodoItem },
  data() {
    return {
      newTodo: '',
      todos: []
    }
  },
  computed: {
    doneCount() {
      return this.todos.filter(todo => todo.done).length;
    }
  },
  methods: {
    addTodo() {
      this.todos.push({ id: this.todos.length + 1, text: this.newTodo, done: false });
      this.newTodo = '';
    },
    deleteDone() {
      this.todos = this.todos.filter(todo => !todo.done);
    },
    deleteAll() {
      this.todos = [];
    }
  },
  mounted() {
    if (localStorage.getItem('todos')) {
      try {
        this.todos = JSON.parse(localStorage.getItem('todos'));
      } catch(e) {
        localStorage.removeItem('todos');
      }
    }
  },
  watch: {
    todos: {
      handler(newTodos) {
        localStorage.setItem('todos', JSON.stringify(newTodos));
      },
      deep: true
    }
  }
}
</script>