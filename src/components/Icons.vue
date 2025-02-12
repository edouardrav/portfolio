<script setup>
import LinkedinIcon from './icons/LinkedinIcon.vue'
import GithubIcon from './icons/GithubIcon.vue'
import MailIcon from './icons/MailIcon.vue'
import MaltIcon from './icons/MaltIcon.vue'
</script>

<template>
  <div class="icons">
    <a href="https://www.linkedin.com/in/edouardrav/" target="_blank" rel="noopener noreferrer">
      <LinkedinIcon />
    </a>
    <a href="https://github.com/edouardrav" target="_blank" rel="noopener noreferrer">
      <GithubIcon />
    </a>
    <a href="https://www.malt.fr/profile/edouardrav" target="_blank" rel="noopener noreferrer">
      <MaltIcon />
    </a>
  </div>
</template>

<style scoped>
.icons {
  display: flex;
  gap: 10px;
  align-items: center;

  a {
    svg {
      fill: var(--charcoal-light);
      width: 30px;
      transition: 0.2s;
    }

    &:hover {
      svg {
        fill: var(--charcoal);

        path {
          fill: var(--lighter-green);
        }
      }
    }
  }
}
</style>
