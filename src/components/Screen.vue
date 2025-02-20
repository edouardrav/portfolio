<script setup>
import { ref } from 'vue'

const props = defineProps({
  color: String,
});

const div = ref(null)

defineExpose({
  div
})
</script>

<template>
  <div class="screen" :style="{ 'border-color': color  }" ref="div">
  </div>
</template>

<style scoped>
.screen {
  border: 4px solid;
  border-radius: 3px;
  width: var(--init-screen-width);
  height: var(--init-screen-height);
  background-size: contain;
}
</style>
