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
  gap: 20px;

  h4 {
    font-size: 2em;
    margin: 0;
    margin-top: -13px;
    color: var(--lighter-green);
  }
  p {
    margin: 0;
    width: 200px;
    font-weight: 300;
  }
}
</style>
