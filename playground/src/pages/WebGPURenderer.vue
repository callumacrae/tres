<script setup lang="ts">
import WebGPURenderer from 'three/examples/jsm/renderers/webgpu/WebGPURenderer';
import { extend, TresCanvas } from '@tresjs/core'
import { TeapotGeometry } from 'three/examples/jsm/geometries/TeapotGeometry.js';
import { MeshBasicNodeMaterial } from 'three/examples/jsm/nodes/Nodes';
// import TheSphere from './TheSphere.vue'
// import { OrbitControls } from '@tresjs/cientos'

const renderer = (canvas: any) => new WebGPURenderer();

extend({ TeapotGeometry, MeshBasicNodeMaterial });
</script>

<template>
  <TresCanvas ref="context" :custom-renderer="renderer">
    <TresPerspectiveCamera :position="[0, 200, 800]" :look-at="[0, 0, 0]" :fov="45" />
    <TresMesh :position="[0, 4, 0]">
      <TresTeapotGeometry :args="[50, 18]" />
      <TresMeshBasicNodeMaterial />
    </TresMesh>
    <TresAmbientLight :intensity="1" />
  </TresCanvas>
</template>
