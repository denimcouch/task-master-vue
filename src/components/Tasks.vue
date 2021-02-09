<template>
  <div class="container">
    <div class="task-list" v-bind:key="task.id" v-for="task in tasks">
      <Task
        v-bind:task="task"
        v-on:del-task="$emit('del-task', task.id)"
        v-on:edit-task="$emit('edit-task', task)"
      />
    </div>
  </div>
</template>

<script>
import Task from "./Task";

export default {
  name: "Tasks",
  props: ["tasks"],
  components: {
    Task
  }
};
</script>

<style>
.container {
  max-width: 1100px;
  margin: auto;
}
.task-list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
