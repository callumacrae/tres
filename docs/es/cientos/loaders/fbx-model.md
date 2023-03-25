# Utilizar `FBXModel`

El componente `FBXModel` es un wrapper sobre [`useFBX`](./use-fbx.md) composable y acepta las mismas opciones de props.

```vue{2,10}
<script setup lang="ts">
import { OrbitControls, FBXModel } from '@tresjs/cientos'
</script>
<template>
  <Suspense>
    <TresCanvas clear-color="#82DBC5" shadows alpha>
      <TresPerspectiveCamera :position="[11, 11, 11]" />
      <OrbitControls />
      <TresScene>
        <FBXModel path="/models/AkuAku.fbx" />
        <TresDirectionalLight :position="[-4, 8, 4]" :intensity="1.5" cast-shadow />
      </TresScene>
    </TresCanvas>
  </Suspense>
</template>
```

## Props

| Prop   | Descripción            | Defacto     |
| :----- | :---------------------- | ----------- |
| `path` | Camino al archivo del modelo. | `undefined` |