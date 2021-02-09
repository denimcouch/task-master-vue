<template>
  <div class="task">
    <h1 class="task__title" v-bind:class="{ checked: task.completed }">
      {{ task.title }}
    </h1>
    <div class="form-input">
      <label for="checkbox">Completed?</label>
      <input class="checkbox" type="checkbox" v-on:change="markComplete" />
    </div>
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
  display: grid;
  grid-template-columns: 6fr 2fr 0.5fr;
  align-items: center;
  justify-content: center;
  width: 100%;
  margin: 1.5rem;
  border-bottom: 1px dotted #aaa;
  padding: 1rem;
}

.task__title {
  font-weight: 200;
  justify-self: left;
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

.form-input {
  display: flex;
  align-items: center;
}

.form-input label {
  margin-right: 10px;
}
</style>
