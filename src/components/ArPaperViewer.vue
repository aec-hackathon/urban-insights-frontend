<template>
  <div class="body">
    <a-scene vr-mode-ui="enabled: false" v-if="modelToShow == 'OBJ Model'" background="color: #ECECEC">
      <a-entity>
        <a-entity light="type:directional; castShadow:true;" :position="sunVectorAframe"></a-entity>
        <a-entity camera="active: true" look-controls wasd-controls position="12 6 12"></a-entity>
        <a-entity
          obj-model="obj: url(/3d/testHouseRotate.obj)"
          position="0 0 0"
          scale="0.05 0.05 0.05"
          shadow="receive: true"
        ></a-entity>
      </a-entity>
    </a-scene>

    <!-- <a-scene vr-mode-ui="enabled: false" v-if="modelToShow == 'Vanilla'" background="color: #ECECEC">
      <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9" shadow></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E" shadow></a-sphere>
      <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D" shadow></a-cylinder>
      <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4" shadow></a-plane>
    </a-scene> -->

    <a-scene vr-mode-ui="enabled: false" v-if="modelToShow == 'Vanilla'" background="color: #ECECEC">
      <a-entity light="type:directional; castShadow:true;" :position="sunVectorAframe"></a-entity>
      <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9" shadow="receive: true"></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E" shadow="receive: true"></a-sphere>
      <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D" shadow="receive: true"></a-cylinder>
      <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4" shadow="receive: true"></a-plane>
    </a-scene>

  </div>
</template>

<script>
export default {
  name: "ArPaper",
  components: {},
  props: {
    modelPath: String,
    vrMode: Boolean,
  },
  computed: {
    modelToShow() {
      return this.$store.state.modelType;
    },
    vrModeString() {
      return "enabled: " + String(this.vrMode);
    },
    sunVectorAframe() {
      return this.$store.state.sunVector;
    },
  },
  methods: {
    testClick() {
      console.log("MODEL PATH", this.modelPath);
    }
  }
};
</script>

<style scoped>
.body {
  font-family: "Benton Sans", "Helvetica Neue", helvetica, arial, sans-serif;
  /* margin: 2em; */
}

/* h1 {
  font-style: italic;
  color: #373fff;
} */
</style>
