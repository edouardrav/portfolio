<script setup>
import LinkedinIcon from './icons/LinkedinIcon.vue'
import GithubIcon from './icons/GithubIcon.vue'
import MailIcon from './icons/MailIcon.vue'
</script>

<template>
  <div class="icons">
    <a href="https://www.linkedin.com/in/edouardrav/" target="_blank" rel="noopener noreferrer">
      <LinkedinIcon />
    </a>
    <a href="https://github.com/edouardrav" target="_blank" rel="noopener noreferrer">
      <GithubIcon />
    </a>
    <a href="mailto:edravelo@gmail.com" target="_blank" rel="noopener noreferrer">
      <MailIcon />
    </a>
  </div>
</template>

<style scoped>
.icons {
  display: flex;
  gap: 10px;


  a {
    svg {
      fill: white;
      width: 25px;
      transition: 0.5s;
    }

    &:hover {
      svg {
        fill: var(--lighter-green);
      }
    }
  }
}
</style>
