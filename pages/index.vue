<template>
  <div id="app">
    <TodoList />
  </div>
</template>
<style lang='scss'>
.todo-header {
  background: gray;
  padding: 10px;
}
.todo-box{
  background: white;
}
.todo-list .todo-box .todo-header .task-count,
.todo-list .todo-box .todo-header .task-done,
.todo-list .todo-box .add-task input,
.todo-list .todo-box .add-task button,
.todo-item i.fa-check-circle,
.todo-item span {
  // Add your custom styles here
}

.todo-items{
  border-radius: 50px;
  margin: 10px;
  border: 1px solid black;
}

.todo-list .todo-box .todo-header .task-count,
.todo-list .todo-box .todo-header .task-done {
  position: relative;
  right: -10px;
  background-color: blue;
  color: white;
  border-radius: 50px;
}
.todo-list .todo-box .todo-header .task-count span.count,
.todo-list .todo-box .todo-header .task-done span.count {
  position: relative;
  right: -5px;
  background-color: white;
  color: blue;
  border-radius: 100%;
  padding-left: 5px;
  padding-right: 5px;
}
.todo-list .todo-box .add-task input,
.todo-list .todo-box .add-task button {
  border-radius: 50px;
}
.todo-list .todo-box .todo-header {
  display: flex;
  justify-content: flex-end;
  column-gap: 10px;
}
.todo-list .todo-box .todo-header button.task-delete,
.todo-list .todo-box .todo-header button.task-delete-all {
  background-color: red;
}
.todo-item, 
.todo-list .todo-box .add-task input, 
.todo-list .todo-box .add-task button, 
.todo-list .todo-box .todo-header div, 
.todo-list .todo-box .todo-header button {
   padding-left: 10px;
   padding-right: 10px;
   margin-right: 10px;
}
.todo-item, 
.todo-list .todo-box .add-task input, 
.todo-list .todo-box .add-task button.add-button, 
.todo-list .todo-box .todo-header div, 
.todo-list .todo-box .todo-header button {
  padding-left: 10px;
  padding-right: 10px;
  margin-right: 10px;
}
.add-task{
  display: flex;
  flex-direction: row;
  margin: 10px;
  height: 40px;
  padding-top: 5px;
  padding-bottom: 5px;
  border: 1px solid black;
  border-radius: 50px;
}
.add-task input{
  width: 100%;
  height: 30px;
}
.add-button{
  background: blue;
  color: white;
}
</style>

<script>
import TodoList from '../components/TodoList.vue'

export default {
  components: { TodoList }
}
</script>