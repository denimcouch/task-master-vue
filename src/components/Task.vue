<template>
  <div class="task" v-bind:class="{ 'checked':task.completed }">
    <h1 class="task__title">{{ task.title }}</h1>
    <input class="checkbox" type="checkbox" v-on:change="markComplete" />
    <button v-on:click="$emit('del-task', task.id)" class="btn btn--delete">x</button>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: ["task"],
  methods: {
    markComplete() {
      console.log("I'm complete!")
      this.task.completed = !this.task.completed;
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
}

.checked {
  text-decoration: line-through;
}

.btn {
  height: 30px;
  width: 30px;
  background: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.btn:focus {
  outline-color: transparent;
}

.btn--delete {
  background: red;
  font-size: 1.4rem;
  font-weight: 700;
  color: rgb(126, 0, 0);
  text-decoration: none;
}
</style>
