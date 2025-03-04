<script setup>
import Work from './Work.vue'

const props = defineProps({
  title: String,
});
</script>

<template>
  <div class="wrap">
    <h2 class="stroke">{{ title }}</h2>
    <div class="category">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.wrap {
  justify-content: flex-start;
  align-items: flex-start;
  padding-bottom: 80px;
  border-bottom: 1px solid #ddd;

  h2 {
    margin: 0;
    font-size: 3em;
    text-align: right;
    margin-right: 20px;
    color: var(--light-green);
    /*transform-origin: 100% 50%;*/
    /*transition: 0.2s;*/
    text-shadow: -3px 3px 0px #00000015;
  }

  .category {
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding: 25px;
    border-radius: 15px;

    p {
      font-size: 1em;
    }
  }
}
</style>
