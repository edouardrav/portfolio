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
import artistsportfolioUrl1 from '../assets/img/works/artistsportfolio.png'

const works = ref([
  {
    title: 'musicadmin',
    info: 'I developed a fullstack rails app to help organize and manage music gigs',
    imgUrls: [musicadminUrl1, musicadminUrl2],
    details: [
      'Ruby on Rails',
      'Stimulus.js',
      'Hotwire',
      'Turbo',
      'PostgreSQL',
    ],
    opened: false,
  },
  {
    title: 'genearbre',
    info: 'I built a dynamic family tree for a genealogy web app',
    imgUrls: [genearbreUrl1, genearbreUrl2],
    details: [
      'Ruby on Rails',
      'Three.js',
      'JavaScript',
      'Tailwind CSS',
    ],
    opened: false,
  },
  {
    title: 'quizz game',
    info: 'I built a quizz game for an energy client',
    imgUrls: [quizzUrl1],
    details: [
      'Vue.js',
      'JavaScript',
      'CSS animations',
    ],
    opened: false,
  },
  {
    title: 'corn app',
    info: 'I worked on the front-end development of an agri-food app',
    imgUrls: [dekalbUrl1, dekalbUrl2],
    details: [
      'React.js',
      'Responsive design',
      'CSS 3',
      'JavaScript',
    ],
    opened: false,
  },
  {
    title: 'artists portfolios',
    info: 'Currently building artists landing pages - more to come!',
    imgUrls: [artistsportfolioUrl1],
    details: [
      'Vue.js',
      'Three.js',
      'JavaScript',
    ],
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
      :details="work.details"
      @click="select(index)">
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
