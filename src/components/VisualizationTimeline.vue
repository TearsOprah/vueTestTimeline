<template>
  <div class="timeline" ref="timeline"></div>
</template>

<script>
import 'vis-timeline/styles/vis-timeline-graph2d.css'
import { Timeline } from 'vis-timeline/standalone'
import pointsData from '@/data/shoot.json'
import { convertDate } from '@/utils/dateConverter'

export default {
  name: 'VisualizationTimeline',
  data() {
    return {
      pointsData: pointsData,
      timeline: null
    }
  },
  mounted() {
    const container = this.$refs.timeline
    const options = {}

    const items = this.pointsData.map((point) => {
      return {
        id: point.id,
        content: `${point.satellite} point ${point.point}`,
        start: convertDate(point.startTimePeriod),
        end: convertDate(point.endTimePeriod),
      }
    })

    this.timeline = new Timeline(container, items, options)
  }
}
</script>

<style>
.timeline {
}

</style>
