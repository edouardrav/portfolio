<script setup>
import { ref, defineExpose } from 'vue'

const div = ref(null)
const props = defineProps({
  color: String,
});

defineExpose({
  div
})
</script>

<template>
  <div class="screen" :style="{ 'border-color': color }" ref="div"></div>
</template>

<style scoped>
:root {
  --init-screen-width: 125px;
  --init-screen-height: 90px;
}

.screen {
  border: 4px solid;
  border-radius: 3px;
  width: var(--init-screen-width);
  height: var(--init-screen-height);
}
</style>
