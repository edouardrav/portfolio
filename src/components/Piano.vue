<script setup>
import { onMounted, useTemplateRef } from 'vue'

const whiteKeys = useTemplateRef('white')
const blackKeys = useTemplateRef('black')
const startDelay = 1000
const keyDelay = 80

const animKeys = (keys) => {
  for (let index = 0; index < keys.length; index++) {
    setTimeout(() => {
      keys[index].classList.add('anim-push')
    }, startDelay + keyDelay * index)
  }
}

onMounted(() => {
  animKeys(whiteKeys.value)
  animKeys(blackKeys.value)
})
</script>

<template>
  <div class="piano">
    <div class="white-keys">
      <div v-for="i in 7" class="white-key" ref="white"></div>
    </div>
    <div class="black-keys">
      <div v-for="i in 5" class="black-key" ref="black"></div>
    </div>
  </div>
</template>

<style scoped>
.piano {
  position: relative;

  .white-keys {
    display: flex;
    gap: 2px;
  }

  .white-key {
    background-color: white;
    width: 17px;
    height: 80px;
    transition: 0.1s;

    &:hover {
      transform: translateY(5px);
    }
  }

  .black-keys {
    position: absolute;
    top: 0;
    display: flex;
    justify-content: center;
    gap: 6px;
  }

  .black-key {
    background-color: var(--charcoal-light);
    width: 14px;
    height: 45px;
    transition: 0.1s;

    &:hover {
      transform: translateY(5px);
    }
  }

  .black-key:nth-child(1) {
    margin-left: 10px
  }

  .black-key:nth-child(3) {
    margin-left: 17px;
  }
}
</style>
