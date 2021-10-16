<template>
  <div class="tasks-grid">
    <template v-if="tasks.length">
      <task v-for="(task, index) in tasks" 
        :key="index" :task="task"
        @status-change="$emit('status-change', index)"
        @delete-task="$emit('delete-task', index)">  
      </task>
    </template>
  </div>
</template>

<script>
import Task from './Task.vue'

export default {
  components: { Task },
  props: {
    tasks: {type: Array, required: true}
  }
}
</script>

<style scoped>

</style>
