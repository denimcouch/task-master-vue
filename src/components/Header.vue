<template>
  <header class="header">
    <h1 class="title title--light">
      <span class="title__text--primary ">Task</span>Master
    </h1>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
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
  width: 100vw;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  margin-bottom: 1rem;
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

#nav a {
  text-decoration: none;
  transition: 0.2s ease-in-out;
}

#nav a:hover {
  color: #22b341;
}
</style>
