<template>
  <div id="app">
    <Header />
    <Tasks v-bind:tasks="tasks" />
  </div>
</template>

<script>
import Header from "./components/Header";
import Tasks from "./components/Tasks";

export default {
  name: "App",
  components: {
    Header,
    Tasks
  },
  data() {
    return {
      tasks: [
        {
          id: 1,
          title: "Take a Shower",
          completed: false
        },
        {
          id: 2,
          title: "Wash the dishes",
          completed: true
        },
        {
          id: 3,
          title: "Take out the trash",
          completed: false
        }
      ]
    };
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

p {
  margin: 0.5rem 0;
}

#app {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  line-height: 1.4;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  line-height: 1.3;
}
</style>
