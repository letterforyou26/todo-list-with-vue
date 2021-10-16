<template>
  <div class="task">
    {{task.content}}
    <button @click="$emit('status-change', task)">V</button>
    <button @click="$emit('delete-task', task)">X</button>
  </div>
</template>

<script>
export default {
  props: {
    task: {type: Object, required: true}
  }
}
</script>

<style scoped>
.task {
  width: 30%;
  height: 100px;
  background-color: #fff;
  color: green;
  
}
</style>
