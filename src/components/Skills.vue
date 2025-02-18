<script setup>
import RailsIcon from './icons/RailsIcon.vue'
import VueIcon from './icons/VueIcon.vue'
import Html5Icon from './icons/Html5Icon.vue'
import CSSIcon from './icons/CSSIcon.vue'
import Skill from './Skill.vue'
import TailwindIcon from './icons/TailwindIcon.vue'
import RubyIcon from './icons/RubyIcon.vue'
import ThreeJSIcon from './icons/ThreeJSIcon.vue'
import JSIcon from './icons/JSIcon.vue'

const cssVars = window.getComputedStyle(document.body)

const fillColor = cssVars.getPropertyValue('--charcoal')
const bgColor = '#fefefe'
</script>

<template>
  <div class="skills">
    <div class="wrap">
      <Skill title="Ruby on Rails">
        <RailsIcon :bgColor="bgColor" :style="{ 'fill': fillColor }" />
      </Skill>
      <Skill title="Vue.js">
        <VueIcon :bgColor="bgColor" :style="{ 'fill': fillColor }" />
      </Skill>
      <Skill title="Three.js">
        <ThreeJSIcon :bgColor="bgColor" :style="{ 'fill': fillColor }" />
      </Skill>
      <Skill title="Tailwind CSS">
        <TailwindIcon :bgColor="bgColor" :style="{ 'fill': fillColor }" />
      </Skill>
      <Skill title="Ruby">
        <RubyIcon :bgColor="bgColor" :style="{ 'fill': fillColor }" />
      </Skill>
      <Skill title="HTML 5">
        <Html5Icon :bgColor="bgColor" :style="{ 'fill': fillColor }" />
      </Skill>
      <Skill title="CSS 3">
        <CSSIcon :bgColor="bgColor" :style="{ 'fill': fillColor }" />
      </Skill>
      <Skill title="JavaScript">
        <JSIcon :bgColor="bgColor" :style="{ 'fill': fillColor }" />
      </Skill>
    </div>
  </div>
</template>

<style scoped>
.skills {
  display: flex;
  justify-content: center;

  .wrap {
    display: grid;
    width: 80%;
    grid-template-columns: repeat(4, 1fr);
    row-gap: 10px;
  }
}
</style>
