<script setup>
import Work from './Work.vue'
</script>

<template>
  <div class="wrap">
    <div class="works">
      <Work title="musicadmin">
        this an amazing app
      </Work>
      <Work title="genearbre">
        this an amazing app
      </Work>
    </div>
    <h2>WORKS</h2>
  </div>
</template>

<style scoped>
.wrap {
  display: flex;
  gap: 50px;
}

.works {
  display: flex;
  flex-direction: column;
  gap: 25px;
}
</style>
