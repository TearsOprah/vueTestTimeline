<template>
  <div class="timeline" ref="timeline"></div>
</template>

<script>
import 'vis-timeline/styles/vis-timeline-graph2d.css';
import { Timeline } from 'vis-timeline/standalone';

export default {
  name: 'VisualizationTimeline',
  mounted() {
    const container = this.$refs.timeline;
    const options = {};
    const items = [
      { id: 1, content: 'Событие 1', start: '2000-01-01' },
      { id: 2, content: 'Событие 2', start: '2005-01-01' },
      { id: 3, content: 'Событие 3', start: '2010-01-01' },
    ];

    const timeline = new Timeline(container, items, options);
  }
};
</script>

<style scoped>
.timeline {
}
</style>
