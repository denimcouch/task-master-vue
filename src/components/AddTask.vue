<template>
  <div class="form-container">
    <form @submit.prevent="addTask">
      <input
        type="text"
        v-model="title"
        name="title"
        placeholder="Add a task..."
      />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTask() {
      const newTask = {
        title: this.title,
        completed: false
      };
      // Send up to parent
      this.$emit("add-task", newTask);

      this.title = "";
    }
  }
};
</script>

<style>
form {
  display: flex;
  max-width: 1100px;
  margin: auto;
}

input[type="text"] {
  flex: 5;
  padding: 5px;
  outline-color: #22b341;
}

input[type="submit"] {
  flex: 1;
}
</style>
