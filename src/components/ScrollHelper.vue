<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  if (!CSS.supports('animation-timeline: scroll()')) {

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

    const content = document.querySelector('.content-anim')
    console.log(content)

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

    const updateHeader = throttle(() => {
      const scrollPercentage = (window.scrollY / (document.documentElement.scrollHeight - window.innerHeight)) * 100;

      for (const animableElement of headerAnimableElements) {
        const domElement = document.querySelector('.' + animableElement)
        if (scrollPercentage >= headerYAnimationTrigger ) {
          domElement.classList.add('scrolled')
        } else if (scrollPercentage < headerYAnimationTrigger) {
          domElement.classList.remove('scrolled')
        }
      }

    }, 8);

    window.addEventListener('scroll', updateHeader, { passive: true })
    updateHeader()

    const updateContentTransform = throttle(() => {
      const scrollPercent = window.scrollY / (document.documentElement.scrollHeight - window.innerHeight);
      const translateY = scrollPercent * parseFloat(getComputedStyle(document.documentElement).getPropertyValue('--content-height'));
      const rotation = getComputedStyle(document.documentElement).getPropertyValue('--rotation-degree');
      content.style.transform = `rotate(${rotation}) translateY(${-translateY}px)`;
    }, 8);

    window.addEventListener('scroll', updateContentTransform, { passive: true });
    updateContentTransform();

  }
})
</script>

<template>
</template>
