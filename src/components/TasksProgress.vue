<template>
  <div class="tasks-progress">
    <div class="progress-border"></div>
    <div class="progress-bar" :style="{width: progress + '%'}"></div>
    <span class="percent-done">{{ progress }}%</span>
  </div>
</template>

<script>
export default {
  props: {
    progress: {type: Number, default: 0}
  }
}
</script>

<style scoped>
.task-progress {
  width: 60%;
}

.progress-border {
  width: 100%;
  height: 30px;
  border: 2px #fff solid;
  border-radius: 3px;
  position: relative;
  z-index: -2;
}

.progress-bar {
  background-color: #fff;
  height: 30px;
  border: 2px #fff solid;
  border-radius: 3px;
  margin: -34px 0px;
  position: relative;
  z-index: -1;
}

.percent-done {
  color: rgb(64, 219, 64);
  font-size: 25px;
}
</style>
