<template>
  <div id="app">
    <TodoList/>
    <TodoListItemDone/>
    <TodoListItem/>
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import TodoListItemDone from './components/TodoListItemDone.vue';
import TodoListItem from './components/TodoListItem.vue';

export default {
  name: "App ,",
  components: {
    TodoList,
    TodoListItemDone,
    TodoListItem,
    
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
