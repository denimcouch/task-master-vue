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
  },
  methods: {
    deleteTask(id) {
      this.tasks = this.tasks.filter(task => task.id !== id);
    },
    addTask(newTask) {
      console.log(newTask);
      this.tasks = [...this.tasks, newTask]
    }
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
