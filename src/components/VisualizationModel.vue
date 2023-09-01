<template>
  <div class="model" ref="cesiumContainer"></div>
</template>

<script>
import {Viewer, Cartesian3, Color, LabelStyle, VerticalOrigin, Cartesian2} from "cesium";
import "cesium/Source/Widgets/widgets.css";

export default {
  name: "VisualizationModel",
  data() {
    return {
      pointsData: []
    };
  },
  mounted() {
    const viewer = new Viewer(this.$refs.cesiumContainer, {
      toolbar: false,
      animation: false,
      timeline: false,
      fullscreenButton: false,
      geocoder: false,
      homeButton: false,
      sceneModePicker: false
    });

    fetch("src/data/points.json")
        .then(response => response.json())
        .then(jsonData => {
          this.pointsData = jsonData;

          // Создание меток для каждой точки
          this.pointsData.forEach(pointData => {
            const longitude = pointData.longitude;
            const latitude = pointData.latitude;
            const height = 0;

            const position = Cartesian3.fromDegrees(longitude, latitude, height);

            const randomColor = Color.fromRandom({alpha: 1.0});

            viewer.entities.add({
              position: position,
              billboard: {
                image: "src/assets/point.svg",
                color: randomColor
              },
              label: {
                text: pointData.label,
                font: "14pt monospace",
                style: LabelStyle.FILL_AND_OUTLINE,
                outlineWidth: 2,
                verticalOrigin: VerticalOrigin.BOTTOM,
                pixelOffset: new Cartesian2(0, -9)
              }
            });
          });
        })
        .catch(() => {
          console.log('Ошибка при загрузке данных')
        });
  }
};
</script>

<style scoped>
.model {
  height: 100%;
}
</style>
