<script setup>
import { ref } from 'vue'
import Work from './Work.vue'
import musicadminUrl1 from '../assets/img/works/musicadmin1.png'
import musicadminUrl2 from '../assets/img/works/musicadmin2.png'
import genearbreUrl1 from '../assets/img/works/genearbre1.png'
import genearbreUrl2 from '../assets/img/works/genearbre2.png'
import dekalbUrl1 from '../assets/img/works/dekalb1.png'
import dekalbUrl2 from '../assets/img/works/dekalb2.png'
import quizzUrl1 from '../assets/img/works/quizz1.png'
import threejsUrl1 from '../assets/img/works/threejs1.png'

const works = ref([
  {
    title: 'musicadmin',
    info: 'a rails app to help organize and manage music gigs',
    imgUrls: [musicadminUrl1, musicadminUrl2],
    classes: '',
  },
  {
    title: 'genearbre',
    info: 'a rails app to manage and vizualize family trees',
    imgUrls: [genearbreUrl1, genearbreUrl2],
    classes: '',
  },
  {
    title: 'quizz game',
    info: 'front-end development for an agri-food client',
    imgUrls: [quizzUrl1],
    classes: '',
  },
  {
    title: 'corn app',
    info: 'front-end development for an agri-food client',
    imgUrls: [dekalbUrl1, dekalbUrl2],
    classes: '',
  },
  {
    title: 'portfolios',
    info: 'exciting three.js projects - more to come!',
    imgUrls: [threejsUrl1],
    classes: '',
  }
])

const previousIndex = ref(null)

const select = (index) => {
  if (index === previousIndex.value) return

  works.value[index].classes = 'open'
  if (previousIndex.value !== null) {
    works.value[previousIndex.value].classes = 'close'
    const previousWork = works.value[previousIndex.value]
    setTimeout(() => {
      previousWork.classes = ''
    }, 200);
  }
  previousIndex.value = index
}
</script>

<template>
  <div class="works">
    <Work v-for="(work, index) in works" :title="work.title" :class="work.classes" :img-urls="work.imgUrls" @click="select(index)">
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
