<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  if (!CSS.supports('animation-timeline: scroll()')) {
    console.log('scroll not suported')

    const animable = [
      'header-anim',
      'hi-anim',
      'rav-anim',
      'name-anim',
      'edouard-anim',
      'im-anim',
      'little-frames-anim'
    ]

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
      console.log('plop')
      const scrollPercentage = (window.scrollY / (document.documentElement.scrollHeight - window.innerHeight)) * 100;
      console.log(window.scrollY)
      console.log(document.documentElement.scrollHeight)
      console.log(window.innerHeight)
      console.log(scrollPercentage)

      for (const animableElement of animable) {
        const domElement = document.querySelector('.' + animableElement)
        if (scrollPercentage >= 13) {
          domElement.classList.add('scrolled')
        } else if (scrollPercentage < 13) {
          domElement.classList.remove('scrolled')
        }
      }

    }, 16);

    window.addEventListener('scroll', updateHeader, { passive: true })
    updateHeader()

  }
})
</script>

<template>
</template>
