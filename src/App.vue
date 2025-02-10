<script setup>
import Piano from './components/Piano.vue'
import Screen from './components/Screen.vue'
import Category from './components/Category.vue'
import Work from './components/Work.vue'
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
    <Category title="works">
      <Work title="musicadmin">
        a rails app to help organize and manage music gigs
      </Work>
      <Work title="genearbre">
        a rails app to manage and vizualize family trees
      </Work>
    </Category>
    <Category title="contact">
      <p class="contact-info">edravelo@gmail.com</p>
      <p class="contact-info">06 31 81 98 00</p>
      <Icons />
    </Category>
  </div>
</template>

<style scoped>
.contact-info {
  margin: 0;
  font-size: 1.5em;
}
</style>
