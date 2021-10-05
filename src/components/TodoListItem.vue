<template>
  <div id="app"> 
    <span v-if="item.done">
      <todo-list-item-done :item="item"></todo-list-item-done>
    </span>
    <span v-else>
      <span>{{ item.message }}</span>
    </span>
    <button @click="removeTask(index)">Remove</button>
    <button @click="doneTask">Done</button>
  </div>
</template>

<script>
import TodoListItemDone from "./TodoListItemDone.vue";
export default {
  components: { TodoListItemDone },
  methods: {
    removeTask: function (id) {
      this.list.splice(id, 1);
      this.nwTask = "";
    },
    doneTask: function () {
      this.item.done = true;
    },
  },

  props: {
    list: Array,
    item: Object,
    index: Number,
    nwTask: String
  },
};
</script>

<style>
</style>