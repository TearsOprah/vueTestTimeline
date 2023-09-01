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
  background-color: #1c1c1d;
  align-items: center;
}
.sidebar__logo {
  width: 100px;
  height: 100px;
  margin: 20px 0 60px;
}
.sidebar__navigation {
  width: 100%;
  border-top: 1px solid rgba(244, 243, 244, 0.8);
  padding-top: 20px;
}
.sidebar__button {
  width: 100%;
  background-color: inherit;
  border: none;
  color: rgba(244, 243, 244, 0.8);
  height: 50px;
  transition: all 0.6s ease;
  text-align: start;
  padding-left: 20px;
  font-size: 16px;
}
.sidebar__button:hover {
  background-color: #2a85e7;
}
.active {
  background-color: #0062cc;
  color: white;
}
</style>
