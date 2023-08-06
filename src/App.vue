<template c>
  <div class="text-center min-h-screen my-10">
    <h1 class="text-white font-bold text-xl my-5">My To Do List</h1>
    <input
      class="p-2 rounded-sm my-2 outline-none"
      v-model="newTask"
      @keyup.enter="addTask"
      placeholder="Add a new task"
    />
    <button class="text-black bg-white p-2 mx-2" @click="addTask">
      Add Task
    </button>

    <ul class="bg-gray-500 mx-auto w-1/2 rounded-lg border-0">
      <li
        v-for="(task, key) in tasks"
        :key="key"
        class="p-4 flex justify-between text-white text-lg capitalize"
      >
        {{ task.text }}
        <button onclick="#" class="justify-end text-red-500">Remove</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: "",
      tasks: [],
    };
  },
  methods: {
    addTask() {
      if (this.newTask.trim === "") return;
      this.tasks.push({ text: this.newTask });
      this.newTask = "";
    },
  },
};
</script>
