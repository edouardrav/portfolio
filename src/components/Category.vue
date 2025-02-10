<script setup>
import Work from './Work.vue'

const props = defineProps({
  title: String,
});
</script>

<template>
  <div class="wrap">
    <div class="category">
      <slot></slot>
    </div>
    <h2 class="stroke">{{ title }}</h2>
  </div>
</template>

<style scoped>
.wrap {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  gap: 50px;
  overflow: hidden;

  h2 {
    margin-right: 20px;
    font-size: 5em;
    color: var(--grey);
    rotate: calc(360deg - var(--rotation-degree));
    transform-origin: 100% 50%;
    margin-bottom: -150px;
    opacity: 0.4;
    transition: 0.2s;
  }

  &:hover {
    h2 {
      /*rotate: 0deg;*/
      transform: translateY(-30px);
      transform-origin: 100% 50%;
      opacity: 1;
    }
  }
}

.category {
  display: flex;
  flex-direction: column;
  gap: 25px;
}
</style>
