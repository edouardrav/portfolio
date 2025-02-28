<script setup>
const props = defineProps({
  title: String,
});
</script>

<template>
  <div class="skill">
    <div class="icon">
      <slot></slot>
    </div>
    <p>{{ title }}</p>
  </div>
</template>

<style scoped>
.skill {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  .icon {
    @media (min-width: 576px) {
      width: 120px;
    }

    @media (max-width: 576px) {
      width: 90px;
    }

    svg {
      border: 1px solid red;
    }

    transition: all 0.2s;
    -webkit-transition: all 0.2s;

    &:hover {
      transform: scale(1.2);
    }
  }

  p {
    margin-top: -10px;
    font-size: 0.8em;
  }
}
</style>
