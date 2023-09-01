<template>
  <div class="sidebar">
    <button @click="showModel">Визуализация</button>
    <button @click="showTimeline">План-график</button>
  </div>
</template>

<script>
export default {
  methods: {
    showModel() {
      this.$emit('changeComponent', 'model');
    },
    showTimeline() {
      this.$emit('changeComponent', 'timeline');
    },
  },
};
</script>

<style scoped>
.sidebar {
  height: 100%;
  width: 250px;
  display: flex;
  flex-direction: column;
}
</style>
