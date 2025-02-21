<script setup>
import { onMounted } from 'vue'

const headerAnimableElements = [
  'header-anim',
  'hi-anim',
  'rav-anim',
  'name-anim',
  'edouard-anim',
  'im-anim',
  'little-frames-anim'
]
const headerYAnimationTrigger = 5

function throttle(func, limit) {
  let inThrottle;
  return function (...args) {
    if (!inThrottle) {
      func.apply(this, args)
      inThrottle = true
      setTimeout(() => inThrottle = false, limit)
    }
  }
}

onMounted(() => {
  if (!CSS.supports('animation-timeline: scroll()')) {

    const updateHeaderScrolling = throttle(() => {
      updateHeader()
    }, 8);

    window.addEventListener('scroll', updateHeaderScrolling, { passive: true })
    updateHeader()

    window.addEventListener('scroll', updateContentTransform, { passive: true });
    updateContentTransform();
  }
})

const updateHeader = () => {
  const scrollPercentage = (window.scrollY / (document.documentElement.scrollHeight - window.innerHeight)) * 100;

  for (const animableElement of headerAnimableElements) {
    const domElement = document.querySelector('.' + animableElement)
    if (scrollPercentage >= headerYAnimationTrigger) {
      domElement.classList.add('scrolled')
      if (animableElement === 'rav-anim') {
        domElement.classList.remove('anim-slide')
      }
    } else if (scrollPercentage < headerYAnimationTrigger) {
      domElement.classList.remove('scrolled')
    }
  }
}

const updateContentTransform = () => {
  const scrollPercent = window.scrollY / (document.documentElement.scrollHeight - window.innerHeight);
  const translateY = scrollPercent * parseFloat(getComputedStyle(document.documentElement).getPropertyValue('--content-translate-y'));
  const rotation = getComputedStyle(document.documentElement).getPropertyValue('--rotation-degree');
  const content = document.querySelector('.content-anim')
  content.style.transform = `rotate(${rotation}) translateY(${translateY}px)`;
}

defineExpose({ updateContentTransform })

//const emit = defineEmits([ updateContentTransform ]);
</script>

<template>
</template>
