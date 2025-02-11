<script setup>
import { ref } from 'vue'
import Work from './Work.vue'

const works = ref([
  {
    title: 'musicadmin',
    info: 'a rails app to help organize and manage music gigs',
    classes: '',
  },
  {
    title: 'genearbre',
    info: 'a rails app to manage and vizualize family trees',
    classes: '',
  },
  {
    title: 'quizz game',
    info: 'front-end development for an agri-food client',
    classes: '',
  },
  {
    title: 'corn app',
    info: 'front-end development for an agri-food client',
    classes: '',
  },
  {
    title: 'portfolios',
    info: 'exciting three.js projects - more to come!',
    classes: '',
  }
])

const previousIndex = ref(null)

const select = (index) => {
  if (index === previousIndex.value) return
  console.log('plop')
  works.value[index].classes = 'open'
  if (previousIndex.value !== null) {
    works.value[previousIndex.value].classes = 'close'
  }
  previousIndex.value = index
}
</script>

<template>
  <div class="works">
    <Work v-for="(work, index) in works" :title="work.title" :class="work.classes" @click="select(index)">
      {{ work.info }}
    </Work>
  </div>
</template>

<style scoped>
.works {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>
