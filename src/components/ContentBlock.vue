<template>
  <div class="content">
    <VisualizationModel v-if="selectedComponent === 'model'" />
    <VisualizationTimeline v-else-if="selectedComponent === 'timeline'" />
  </div>
</template>

<script>
import VisualizationModel from '@/components/VisualizationModel.vue'
import VisualizationTimeline from '@/components/VisualizationTimeline.vue'

export default {
  name: 'ContentBlock',
  props: {
    selectedComponent: String
  },
  components: {
    VisualizationTimeline,
    VisualizationModel
  }
}
</script>

<style>
.content {
  width: 100%;
  height: 100%;
  overflow-y: auto;
}
</style>
