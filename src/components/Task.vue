<template>
  <div class="task">
    <div class="columns is-multiline">
      <div v-for="(task, index) in tasks" :key="index" class="column is-4">
        <article class="message">
          <div class="message-header">
            <p>{{ task.title }}</p>
            <button class="delete" aria-label="delete"></button>
          </div>
          <div class="message-body">
            {{ task.body }}
          </div>
        </article>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    tasks: Array,
  },
};
</script>

<style scoped></style>
