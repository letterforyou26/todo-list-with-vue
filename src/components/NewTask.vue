<template>
  <div class="new-task">
    <input type="text" v-model="name">
    <button @click="addTask" @keydown.enter="addTask">+</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: ''
    }
  },
  methods: {
    addTask() {
      this.$emit('add-task', {name: this.name});
      this.name = ''
    }
  }
}
</script>

<style scoped>

</style>
