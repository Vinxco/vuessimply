<template>
  <div>
    <form id="app" @submit.prevent="createTask">
      <label class="label" for="task">Nueva tarea: </label>
      <input id="task" v-model="newTask" type="text" />

      <input type="submit" value="crear tarea" />
    </form>
    <pre>
       {{ $data }}
    </pre>
  </div>
</template>

<script>
export default {
  data: () => ({
    newTask: "",
    tasks: []
  }),
  methods: {
    createTask() {
      let task = {
        text: this.newTask,
        completed: false
      };
      this.tasks.push(task);
      this.newTask = "";
      console.log(this.tasks);
    }
  }
};
</script>

<style></style>
