<template>
  <div class="page">
    <SidebarBlock @changeComponent="changeComponent" :activeComponent="selectedComponent" />
    <ContentBlock :selectedComponent="selectedComponent" />
  </div>
</template>

<script>
import SidebarBlock from '@/components/SidebarBlock.vue'
import ContentBlock from '@/components/ContentBlock.vue'

export default {
  data() {
    return {
      selectedComponent: 'model'
    }
  },
  components: {
    SidebarBlock,
    ContentBlock
  },
  methods: {
    changeComponent(componentName) {
      this.selectedComponent = componentName
    }
  }
}
</script>

<style scoped>
.page {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-columns: auto 1fr;
}
</style>
