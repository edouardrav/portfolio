<script setup>
import Screen from './Screen.vue'

const props = defineProps({
  title: String,
});
</script>

<template>
  <div class="work">
    <Screen />
    <div class="info">
      <h4>{{ title }}</h4>
      <p>
        <slot></slot>
      </p>
    </div>
  </div>
</template>

<style scoped>
.work {
  display: flex;
  gap: 10px;

  h4 {
    font-size: 2em;
    margin: 0;
    margin-top: -13px;
  }
  p {
    margin: 0;
    color: #222;
  }
}
</style>
