<script setup>
import { ref, watch, computed, useTemplateRef, onMounted } from 'vue'
import Screen from './Screen.vue'

const props = defineProps({
  title: String,
  details: Array,
  imgUrls: {
    type: Array,
    required: true,
  },
  opened: {
    type: Boolean,
    required: true
  }
});
const classes = ref('')

const screen = useTemplateRef('screen')
const currentImgIndex = ref(0)
let carouselTimeout
const carouselDelay = 1000

function updateImg() {
  if (props.imgUrls.length === 1) return

  currentImgIndex.value += 1
  if (currentImgIndex.value > props.imgUrls.length - 1) {
    currentImgIndex.value = 0
  }
  carouselTimeout = setTimeout(() => {
    props.opened && props.imgUrls.length > 1 && updateImg()
  }, carouselDelay);
}

const detailsWrap = useTemplateRef("detailsWrap")
const detailsItems = useTemplateRef('details')
let detailsTimeout
const detailsDelay = parseInt(getComputedStyle(document.documentElement).getPropertyValue('--details-delay'));

watch(() => props.opened,
  (opened) => {
    opened ? classes.value = 'open' : classes.value = 'close'
    if (opened) {
      carouselTimeout = setTimeout(() => {
        updateImg()
      }, carouselDelay)
      detailsTimeout = setTimeout(() => {
        detailsWrap.value.classList.remove("hide")
        for (let i = 0; i < detailsItems.value.length; i++) {
          const detail = detailsItems.value[i]
          setTimeout(() => {
            detail.classList.add("detailsAnim")
          }, 100 * i);
        }
      }, detailsDelay);
    } else {
      setTimeout(() => {
        classes.value = ''
      }, 220);
      clearTimeout(carouselTimeout)
      currentImgIndex.value = 0
      clearTimeout(detailsTimeout)
      for (const detail of detailsItems.value) {
        detail.classList.remove("detailsAnim")
      }
      detailsWrap.value.classList.add("hide")
    }
  }
)

const currentImgUrl = computed(() => {
  return `url(${props.imgUrls[currentImgIndex.value]})`
})

</script>

<template>
  <div :class="['work', classes]">
    <Screen class="screen" ref="screen" :style="{ '--hover-img': currentImgUrl }" />
    <div class="info">
      <h4>{{ title }}</h4>
      <p>
        <slot></slot>
      </p>
      <div class="details hide" ref="detailsWrap">
        <p v-for="detail in details" ref="details">› {{ detail }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.work {
  display: flex;
  gap: 18px;

  &.open {
    @media (max-width: 576px) {
      flex-direction: column;
      margin-bottom: 10px;

      .info {
        margin-left: 5px;
      }
    }

    .screen {
      animation: animGrow 0.2s ease forwards;

      &::before {
        opacity: 1 !important;
        filter: grayscale(0%) !important;
        -webkit-filter: grayscale(0%) !important;
        -moz-filter: grayscale(0%) !important;
        -ms-filter: grayscale(0%) !important;
        -o-filter: grayscale(0%) !important;
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

  .details {
    margin-top: 20px;
    display: flex;
    flex-direction: column;
    gap: 5px;

    &.hide {
      display: none !important;
    }

    p {
      font-family: 'iAQuattro-Italic';
      color: var(--charcoal);
      opacity: 0;

      &.detailsAnim {
        animation: detailsAnim 0.2s ease forwards;
      }
    }
  }

  .screen {
    position: relative;
    transition: 0.1s;
    -webkit-transition: 0.1s;

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
      -webkit-transition: 0.1s;

      filter: grayscale(100%);
      -webkit-filter: grayscale(100%);
      -moz-filter: grayscale(100%);
      -ms-filter: grayscale(100%);
      -o-filter: grayscale(100%);
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
        opacity: 1;
      }
    }
  }
}
</style>
