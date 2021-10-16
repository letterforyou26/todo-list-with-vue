<template>
  <div id="app">
    <h1>Todo List</h1>
    <tasks-progress :progress="progress"></tasks-progress>
    <new-task @add-task="addTask"></new-task>
    <tasks-grid :tasks="tasks"
      @status-change="statusChange"
      @delete-task="deleteTask">
    </tasks-grid>
  </div>
</template>

<script>
import TasksGrid from './components/TasksGrid.vue'
import TasksProgress from './components/TasksProgress.vue'
import NewTask from './components/NewTask.vue'

export default {
  data() {
    return {
      tasks: [
        {content: "test1", done: true},
        {content: "test2", done: false}
      ]
    }
  },
  methods: {
    addTask(task) {
      const content = task.name;
      this.tasks.push({
        content: content,
        done: false
      })
    },
    statusChange(index) {
      this.tasks[index].done = !this.tasks[index].done;
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    }
  },
  components: {
    TasksGrid,
    TasksProgress,
    NewTask
  },
  computed: {
    progress() {
      const totalTask = this.tasks.length;
      const doneTask = this.tasks.filter(t => t.done).length;
      return Math.round(doneTask / totalTask * 100) || 0;
    }
  }
}
</script>

<style>
body {
  background-image: linear-gradient(to right, rgba(240, 41, 230, 1), rgba(240, 41, 230,0.5));
  font-family: 'Lato', sans-serif;
  display: flex;
  justify-content: center;
}

#app {
  width: 60%;
  background-color: transparent;
  color: #fff;
}

#app h1 {
  font-size: 45px;
}
</style>
