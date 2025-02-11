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
  /*display: flex;*/
  justify-content: flex-start;
  align-items: flex-start;
  /*gap: 50px;*/
  overflow: hidden;
  border-bottom: 1px solid var(--charcoal-light);

  h2 {
    /*display: none;*/
    /*position: absolute;*/
    margin:0;
    /*margin-right: 20px;*/
    font-size: 3em;
    text-align: right;
    margin-right: -8px;
    color: var(--charcoal-light);
    /*rotate: calc(360deg - var(--rotation-degree));*/
    transform-origin: 100% 50%;
    /*margin-bottom: -150px;*/
    /*opacity: 0.2;*/
    transition: 0.2s;
  }

  &:hover {
    h25 {
      /*rotate: 0deg;*/
      transform: translateY(-30px);
      transform-origin: 100% 50%;
      opacity: 0.6;
    }
  }
}

.category {
  display: flex;
  flex-direction: column;
  gap: 10px;
  padding: 25px;
  border-radius: 15px;
}
</style>
