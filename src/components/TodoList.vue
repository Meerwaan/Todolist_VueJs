<template>
  <div class="todolist" id="app">
    <ol>
      <li v-for="(item, index) in list" :key="item.message">
        <todo-list-item :nwTask="nwTask" :list="list" :item="item" :index="index"></todo-list-item>
      </li>
    </ol>
    <form action="" @submit.prevent="addTask">
      <input type="text" v-model="nwTask" />
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
      nwTask: "",
      list: [{
        message: "Faire une liste de course",
        done: false
      }],
    };
  },
  methods: {
    addTask: function () {
      this.list.push({
        message: this.nwTask,
        done: false,
      });
      this.nwTask = "";
    },
  },
};
</script>

<style>
</style>