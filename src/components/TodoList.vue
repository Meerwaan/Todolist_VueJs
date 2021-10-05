<template>
  <div class="todolist" id="app">
    <ol>
      <li v-for="(item, index) in list" :key="item.message">
        <todo-list-item :newTask="newTask" :list="list" :item="item" :index="index"></todo-list-item>
      </li>
    </ol>
    <form action="" @submit.prevent="addTask">
      <input type="text" v-model="newTask" />
      <input type="submit" value="Ajouter une tâche" />
    </form>
  </div>
</template>

<script>
import TodoListItem from './TodoListItem.vue';

export default {
  components: { TodoListItem },
  data() {
    return {
      newTask: "",
      list: [{
        message: "Faire une liste de course",
        done: false
      }],
    };
  },
  methods: {
    addTask: function () {
      this.list.push({
        message: this.newTask,
        done: false,
      });
      this.newTask = "";
    },
  },
};
</script>

<style>
</style>