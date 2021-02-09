<template>
  <div class="task">
    <h1 class="task__title" v-bind:class="{ checked: task.completed }">
      {{ task.title }}
    </h1>
    <input class="checkbox" type="checkbox" v-on:change="markComplete" />
    <button v-on:click="$emit('del-task', task.id)" class="btn btn--delete">
      x
    </button>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: ["task"],
  methods: {
    markComplete() {
      this.task.completed = !this.task.completed;
      this.$emit("edit-task", this.task);
    }
  }
};
</script>

<style>
.task {
  display: flex;
  flex-direction: row-reverse;
  align-items: center;
  justify-content: space-between;
  width: 50%;
  margin: 1.5rem;
  border-bottom: 1px dotted #aaa;
  padding: 1rem;
}

.task__title {
  font-weight: 300;
}

.checkbox {
  height: 30px;
  width: 30px;
  border-radius: 5px;
  cursor: pointer;
}

.checked {
  text-decoration: line-through;
}
</style>
