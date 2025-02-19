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
    opened: false,
  },
  {
    title: 'genearbre',
    info: 'a rails app to manage and vizualize family trees',
    imgUrls: [genearbreUrl1, genearbreUrl2],
    opened: false,
  },
  {
    title: 'quizz game',
    info: 'front-end development for an agri-food client',
    imgUrls: [quizzUrl1],
    opened: false,
  },
  {
    title: 'corn app',
    info: 'front-end development for an agri-food client',
    imgUrls: [dekalbUrl1, dekalbUrl2],
    opened: false,
  },
  {
    title: 'portfolios',
    info: 'exciting three.js projects - more to come!',
    imgUrls: [threejsUrl1],
    opened: false,
  }
])

const previousIndex = ref(null)

const select = (index) => {
  if (index === previousIndex.value) return

  works.value[index].opened = true

  if (previousIndex.value !== null) {
    works.value[previousIndex.value].opened = false
    const previousWork = works.value[previousIndex.value]
  }
  previousIndex.value = index
}
</script>

<template>
  <div class="works">
    <Work v-for="(work, index) in works" 
      :title="work.title"
      :img-urls="work.imgUrls"
      :opened="work.opened"
      @click="select(index)"
    >
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
