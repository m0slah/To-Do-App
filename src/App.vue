<template c>
  <div class="text-center min-h-screen my-10">
  <h1 class="text-white font-bold text-xl my-5">My To Do List</h1>
    <ul class="border-2 bg-blue-200 mx-auto w-1/2 rounded-lg border-0">
      <li
        v-for="(task, key) in tasks"
        :key="key"
        class="p-4 text-center"
      >
        {{ task }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tasks: [(name = "study")],
    };
  },
};
</script>
