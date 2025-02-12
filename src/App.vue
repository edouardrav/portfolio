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
        <strong>ruby on rails</strong>
        <strong>vue.js</strong>
        <strong>three.js</strong>
      </div>
      <p class="tab">I can't keep my hands off of <strong>keyboards</strong>.</p>
    </Category>
    <Category title="works">
      <Works />
    </Category>
    <Category class="contact" title="contact">
      <p class="contact-info">edravelo@gmail.com</p>
      <Icons />
    </Category>
  </div>
</template>

<style scoped>
.me {
  padding-bottom: 50px;
}
.tab {
  margin-top: 50px;
  text-align: center;
}
.contact-info {
  margin: 0;
  font-size: 1.5em;
}

.content {
  width: 650px;
  transform: rotate(var(--rotation-degree));
  background-color: #ffffffaa;
  padding-top: 180px;
  margin-top: -130px;
  display: flex;
  flex-direction: column;
  gap: 30px;

  p {
    font-size: 1em;
  }

  strong {
    font-family: 'CabinetGrotesk-Bold';
    color: var(--charcoal);
    font-size: 1.4em;
    font-weight: 500;
  }

  .techs {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin-left: 320px;
  }
}

.contact {
  padding-bottom: 70px;
}
</style>
