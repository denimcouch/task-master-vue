<template>
  <header class="header">
    <h1 class="title title--light">
      <span class="title__text--primary ">Task</span>Master
    </h1>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style>
.header {
  background: #fff;
  color: #333;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.title {
  font-size: 3rem;
}

.title__text--primary {
  color: #22b341;
}

.title--light {
  font-weight: 400;
}
</style>
