<script setup>
import { useTemplateRef } from 'vue'
import Screen from './Screen.vue'

const props = defineProps({
  title: String,
  imgUrls: Array
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
    <Screen class="screen" ref="screen" :img-urls="imgUrls" />
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
  gap: 18px;

  &.open {
    .screen {
      animation: animGrow 0.2s ease forwards;

      &::before {
        opacity: 1 !important;
      }
    }
  }

  &.close {
    .screen {
      animation: animShrink 0.2s ease forwards;
    }
  }

  img {
    border: 1px solid red;
    width: 100px;
  }

  h4 {
    font-family: 'CabinetGrotesk-Bold';
    /*letter-spacing: 1px;*/
    font-size: 1.3em;
    margin: 0;
    margin-top: -7px;
    color: var(--charcoal-light);
    transition: 0.2s;
  }

  p {
    margin: 0;
    width: 200px;
    font-size: 1em;
  }

  .screen {
    position: relative;
    transition: 0.1s;

    &::before {
      content: ' ';
      display: block;
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      opacity: 0;
      background-image: var(--hover-img);
      background-repeat: no-repeat;
      background-position: 50% 0;
      background-size: cover;
      transition: 0.1s;
    }
  }

  &:hover {
    cursor: pointer;

    h4 {
      color: var(--charcoal);
    }

    .screen {
      width: 150px;

      &::before {
        opacity: 0.5;
      }
    }
  }
}
</style>
