<script setup>
import Piano from './components/Piano.vue'
import Screen from './components/Screen.vue'
import Works from './components/Works.vue'
</script>

<template>
  <header>
    <div class="headwrap">
      <div class="name">
        <p>I'm</p>
        <p>EDOUARD</p>
        <p class="rav stroke anim-slide">RAV.</p>
      </div>
      <div class="hi">
        <h1 class="anim-raise">Hi!</h1>
        <div class="flex">
          <div class="frames">
            <Screen />
            <Piano />
          </div>
          <p>pianist & <br>web developer</p>
        </div>
      </div>
    </div>
  </header>
  <div class="content">
    <div class="me">
      <p>I play <strong>jazz</strong> and I build <strong>web apps</strong> with</p>
      <div class="techs">
        <strong>ruby on rails</strong>
        <br /><strong>vue.js</strong>
        <br /><strong>three.js</strong>
        <p>(and all kind of keyboards)</p>
      </div>
    </div>
    <Works />
  </div>
</template>

<style scoped></style>
