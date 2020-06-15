<template>
  <div class="home">
    <section class="hero is-fullheight is-light is-bold">
      <div class="hero-body">
        <div class="container">
          <h1 class="title has-text-centered is-size-1">
            Your Task Tracker
          </h1>
          <h2 class="subtitle has-text-centered is-size-4">
            Your 3 latest Tasks
          </h2>
          <!-- Insert Task Component -->
          <Task :tasks="tasks" />
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import axios from 'axios';
import Task from '@/components/Task';
export default {
  name: 'Home',
  data() {
    return {
      tasks: null,
    };
  },
  components: {
    Task,
  },
  methods: {
    async getTasks() {
      const response = await axios.get(
        'https://jsonplaceholder.typicode.com/todos'
      );
      const topTasks = response.data.slice(0, 3);
      this.tasks = topTasks;
    },
  },
  mounted() {
    this.getTasks();
  },
};
</script>
