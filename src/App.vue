<template>
  <div class="page">
    <Sidebar @changeComponent="changeComponent" />
    <Content :selectedComponent="selectedComponent" />
  </div>
</template>

<script>
import Sidebar from '@/components/Sidebar.vue';
import Content from '@/components/Content.vue';

export default {
  data() {
    return {
      selectedComponent: 'model',
    };
  },
  components: {
    Sidebar,
    Content,
  },
  methods: {
    changeComponent(componentName) {
      this.selectedComponent = componentName;
    },
  },
};
</script>

<style scoped>
.page {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-columns: auto 1fr;
}
</style>
