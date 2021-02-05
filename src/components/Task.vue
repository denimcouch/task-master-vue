<template>
  <div class="task">
    <h1>{{ task.title }}</h1>
    <input class="btn" type="checkbox" />
  </div>
</template>

<script>
export default {
  name: "Task",
  props: ["task"],
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
</style>
