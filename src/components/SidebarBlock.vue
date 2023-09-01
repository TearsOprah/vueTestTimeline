<template>
  <div class="sidebar">
    <img class="sidebar__logo" src="src/assets/logo.svg" alt="logo" />
    <nav class="sidebar__navigation">
      <button
        class="sidebar__button"
        @click="showModel"
        :class="{ active: activeComponent === 'model' }"
      >
        Визуализация
      </button>
      <button
        class="sidebar__button"
        @click="showTimeline"
        :class="{ active: activeComponent === 'timeline' }"
      >
        План-график
      </button>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'SidebarBlock',
  props: {
    activeComponent: String
  },
  methods: {
    showModel() {
      this.$emit('changeComponent', 'model')
    },
    showTimeline() {
      this.$emit('changeComponent', 'timeline')
    }
  }
}
</script>

<style scoped>
.sidebar {
  height: 100%;
  width: 250px;
  display: flex;
  flex-direction: column;
  background-color: var(--color-background);
  align-items: center;
}
.sidebar__logo {
  width: 100px;
  height: 100px;
  margin: 20px 0 60px;
}
.sidebar__navigation {
  width: 100%;
  border-top: 1px solid var(--color-text);
  padding-top: 20px;
}
.sidebar__button {
  width: 100%;
  background-color: inherit;
  border: none;
  color: var(--color-text);
  height: 50px;
  transition: all 0.6s ease;
  text-align: start;
  padding-left: 20px;
  font-size: 16px;
}
.sidebar__button:hover {
  background-color: var(--color-button-hover);
}
.active {
  background-color: var(--color-button-active);
  color: white;
}
@media (max-width: 600px) {
  .sidebar {
    width: 120px;
  }
  .sidebar__logo {
    width: 60px;
    height: 60px;
    margin: 20px 0 40px;
  }
  .sidebar__button {
    height: 40px;
    padding-left: 10px;
    font-size: 12px;
  }
}
</style>
