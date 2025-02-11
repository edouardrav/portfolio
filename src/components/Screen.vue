<script setup>
import { ref, defineExpose } from 'vue'

const div = ref(null)

defineExpose({
  div
})
</script>

<template>
  <div class="screen" ref="div"></div>
</template>

<style scoped>
:root {
  --init-screen-width: 125px;
  --init-screen-height: 90px;
}

.screen {
  border: 4px solid white;
  border-radius: 0 0 0 0;
  width: var(--init-screen-width);
  height: var(--init-screen-height);
}
</style>
