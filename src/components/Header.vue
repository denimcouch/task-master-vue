<template>
  <header class="header">
    <h1 class="title"><span class="title__text--primary">Task</span> Master</h1>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style>
.header {
  background: #333;
  color: #fff;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.title {
  font-size: 3rem;
}

.title__text--primary {
  color: #1e8e36;
}
</style>
