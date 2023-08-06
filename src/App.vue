<template c>
  <div class="text-center min-h-screen my-10">
    <h1 class="text-white font-bold text-xl my-5">My To Do List</h1>
    <input
      class="p-2 rounded-sm my-2 outline-none"
      v-model="newTask"
      @keyup.enter="addTask"
      placeholder="Add a new task"
    />
    <button
      class="text-white bg-green-300 p-2 mx-2 hover:opacity-90"
      @click="addTask"
    >
      Add Task
    </button>

    <ul class="bg-gray-500 mx-auto w-1/2 rounded-lg border-0">
      <li
        v-for="(task, key) in tasks"
        :key="key"
        class="p-4 flex justify-between text-lg capitalize"
      >
        <label class="flex items-center">
          <input
            type="checkbox"
            v-model="task.completed"
            class="mr-2 w-4 h-4 border-gray-300 rounded-sm mr-2"
          />
          <span
            class="text-white"
            :style="{
              textDecoration: task.completed ? 'line-through' : 'none',
            }"
            >{{ task.text }}</span
          >
        </label>
        <button @click="removeTask(key)" class="text-red-500">Remove</button>
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
    removeTask(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>
