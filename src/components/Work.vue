<script setup>
import { useTemplateRef } from 'vue'
import Screen from './Screen.vue'

const props = defineProps({
  title: String,
});

const screen = useTemplateRef('screen')

const grow = (event) => {
  screen.value.div.classList.add('anim-grow')
}

const shrink = () => {
  screen.value.div.classList.add('anim-shrink')
}
</script>

<template>
  <div class="work">
    <Screen class="screen" ref="screen" />
    <div class="info">
      <h4>{{ title }}</h4>
      <p>
        <slot></slot>
      </p>
    </div>
  </div>
</template>

<style scoped>
.work {
  display: flex;
  gap: 20px;

  &.open {
    .screen {
      animation: animGrow 0.2s ease forwards;
    }
  }

  &.close {
    .screen {
      animation: animShrink 0.2s ease forwards;
    }
  }

  h4 {
    font-family: 'CabinetGrotesk-Bold';
    font-size: 2em;
    margin: 0;
    margin-top: -13px;
    color: var(--charcoal-light);
    transition: 0.2s;
  }

  p {
    margin: 0;
    width: 200px;
    font-weight: 300;
  }

  .screen {
    transition: 0.2s;
  }

  &:hover {
    cursor: pointer;

    h4 {
      color: var(--charcoal-light);
    }

    .screen {
      background-color: var(--light-green);
    }
  }
}
</style>
