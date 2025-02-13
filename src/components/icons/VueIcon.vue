<script setup>
const props = defineProps({
  bgColor: String
});
</script>

<template>
  <svg fill="#000000" viewBox="-9.36 -9.36 42.72 42.72" xmlns="http://www.w3.org/2000/svg">
    <g id="SVGRepo_bgCarrier" stroke-width="0" transform="translate(4.08,4.08), scale(0.66)">
      <path transform="translate(-9.36, -9.36), scale(2.67)" :fill="bgColor"
        d="M9.166.33a2.25 2.25 0 00-2.332 0l-5.25 3.182A2.25 2.25 0 00.5 5.436v5.128a2.25 2.25 0 001.084 1.924l5.25 3.182a2.25 2.25 0 002.332 0l5.25-3.182a2.25 2.25 0 001.084-1.924V5.436a2.25 2.25 0 00-1.084-1.924L9.166.33z"
        strokewidth="0"></path>
    </g>
    <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
    <g id="SVGRepo_iconCarrier">
      <path
        d="M19.1143 2H15L12 6.9L9.42857 2H0L12 23L24 2H19.1143ZM3 3.75H5.91429L12 14.6L18.0857 3.75H21L12 19.5L3 3.75Z"></path>
    </g>
  </svg>
</template>
