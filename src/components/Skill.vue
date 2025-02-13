<script setup>
const props = defineProps({
  title: String,
});
</script>

<template>
  <div class="skill">
    <div class="icon">
      <slot></slot>
    </div>
    <p>{{ title }}</p>
  </div>
</template>

<style scoped>
.skill {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  .icon {
    width: 120px;
  }

  p {
    margin-top: -10px;
    font-size: 0.8em;
  }
}
</style>
