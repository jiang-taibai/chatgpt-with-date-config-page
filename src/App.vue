<script setup>

import Simulation from "./components/Stimulation/Simulation.vue";
import {dialogue0, dialogue1} from "./assets/Messages.js";

</script>

<template>
  <div class="preview">
    <simulation class="preview-item" :dark="false" :dialogue="dialogue0"/>
    <simulation class="preview-item" :dark="true" :dialogue="dialogue1"/>
  </div>
</template>

<style lang="less">
.preview {
  display: flex;
  flex-direction: row;

  .preview-item {
    width: 50%;
  }
}

.editing {
  background: #F0F0F0;
  height: 200px;
}
</style>
