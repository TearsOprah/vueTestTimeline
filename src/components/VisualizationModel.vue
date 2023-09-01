<template>
  <div class="model" ref="cesiumContainer"></div>
</template>

<script>
import { Viewer } from "cesium";
import "cesium/Source/Widgets/widgets.css";

export default {
  name: "VisualizationModel",
  mounted() {
    const viewer = new Viewer(this.$refs.cesiumContainer);
    viewer.scene.debugShowFramesPerSecond = true;
  }
};
</script>

<style scoped>
.model {
  height: 100%;
}
</style>
