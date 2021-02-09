<template>
  <div id="app">
    <Header />
    <AddTask v-on:add-task="addTask" />
    <Tasks v-bind:tasks="tasks" v-on:del-task="deleteTask" />
  </div>
</template>

<script>
import Header from "./components/Header";
import Tasks from "./components/Tasks";
import AddTask from "./components/AddTask";

export default {
  name: "App",
  components: {
    Header,
    AddTask,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id);
    },
    addTask(newTask) {
      console.log(newTask);
      const taskOptions = {
        method:"POST",
        headers: {
          "Content-Type": "application/json",
          Accept: "application/json"
        },
        body: JSON.stringify(newTask)
      };
      fetch("http://localhost:3000/tasks", taskOptions)
      .then(res => res.json())
      .then(task => this.tasks = [...this.tasks, task])
    }
  },
  created() {
    fetch("http://localhost:3000/tasks")
    .then(res => res.json())
    .then(tasks => this.tasks = tasks)
    .catch(err => console.log(err));
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

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 0.5rem 1.5rem;
  transition: 0.4s ease-in-out;
  cursor: pointer;
}

.btn:hover {
  opacity: 0.9;
}

.btn:focus {
  outline-color: transparent;
}

.btn--delete {
  background: red;
  font-size: 1.4rem;
  font-weight: 700;
  color: rgb(126, 0, 0);
  text-transform: none;
}
</style>
