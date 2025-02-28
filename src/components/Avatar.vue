<script setup>
import imgAvatar from '../assets/img/ed.png'

const imgUrl = imgAvatar
</script>

<template>
  <img :src="imgUrl" alt="" class="avatar">
</template>

<style scoped>
@media (min-width: 576px) {
  img.avatar {
    width: 200px;
  }
}

@media (max-width: 576px) {
  img.avatar {
    width: 120px;
  }
}

img.avatar {
  border-radius: 50%;
  transform: rotate(10deg);
}
</style>
