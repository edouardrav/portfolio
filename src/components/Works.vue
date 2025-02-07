<script setup>
import Work from './Work.vue'
</script>

<template>
  <div class="wrap">
    <div class="works">
      <Work title="musicadmin">
        a rails app to help organize and manage music gigs
      </Work>
      <Work title="genearbre">
        a rails app to manage and vizualize family trees
      </Work>
    </div>
    <h2 class="stroke">WORKS</h2>
  </div>
</template>

<style scoped>
.wrap {
  display: flex;
  gap: 50px;

  h2 {
    margin: 0;
    font-size: 3.5em;
    color: var(--darker-green);
    -webkit-text-stroke-color: var(--lighter-green);
    -webkit-text-stroke-width: 4px;
    letter-spacing: 3px;
    margin-top: -10px;

  }
}

.works {
  display: flex;
  flex-direction: column;
  gap: 25px;
}
</style>
