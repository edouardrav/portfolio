<script setup>
import imgAvatar from '../assets/img/ed.png'

const imgUrl = imgAvatar
</script>

<template>
  <img :src="imgUrl" alt="" class="avatar">
</template>

<style scoped>
img.avatar {
  width: 200px;
  border-radius: 50%;
  transform: rotate(10deg);
}
</style>
