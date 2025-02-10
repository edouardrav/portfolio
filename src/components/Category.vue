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
  gap: 50px;

  h2 {
    margin: 0;
    font-size: 3.5em;
    color: var(--darker-grey);
    margin-top: -19px;
  }
}

.category {
  display: flex;
  flex-direction: column;
  gap: 25px;
}
</style>
