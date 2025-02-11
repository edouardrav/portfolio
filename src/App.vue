<script setup>
import Piano from './components/Piano.vue'
import Screen from './components/Screen.vue'
import Category from './components/Category.vue'
import Works from './components/Works.vue'
import Icons from './components/Icons.vue'
</script>

<template>
  <header>
    <div class="headwrap">
      <div class="name">
        <p>I'm</p>
        <p>EDOUARD</p>
        <p class="rav stroke anim-slide">rav.</p>
      </div>
      <div class="hi">
        <h1 class="anim-raise">Hi!</h1>
        <div class="flex">
          <div class="frames">
            <Screen color="white" />
            <Piano />
          </div>
          <p>pianist & <br>web developer</p>
        </div>
      </div>
    </div>
  </header>
  <div class="content">
    <Category class="me">
      <p>I play <strong>jazz</strong> and I build <strong>web apps</strong> with</p>
      <div class="techs">
        <Screen />
        <div>
          <strong>ruby on rails</strong>
          <br /><strong>vue.js</strong>
          <br /><strong>three.js</strong>
        </div>
      </div>
      <p>(I can't keep my hands off of keyboards)</p>
    </Category>
    <Category title="works">
      <Works />
    </Category>
    <Category title="contact">
      <p class="contact-info">edravelo@gmail.com</p>
      <p class="contact-info">06 31 81 98 00</p>
      <Icons />
    </Category>
  </div>
</template>

<style scoped>
.me p {
  margin-top: 0;
}

.contact-info {
  margin: 0;
  font-size: 1.5em;
}
</style>
