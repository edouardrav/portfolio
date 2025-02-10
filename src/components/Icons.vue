<script setup>
import LinkedinIcon from './icons/LinkedinIcon.vue'
import GithubIcon from './icons/GithubIcon.vue'
import MailIcon from './icons/MailIcon.vue'
</script>

<template>
  <div class="icons">
    <LinkedinIcon />
    <GithubIcon />
    <MailIcon />
  </div>
</template>

<style scoped>
.icons {
  display: flex;
  gap: 10px;

  svg {
    fill: white;
    width: 25px;
  }
}
</style>
