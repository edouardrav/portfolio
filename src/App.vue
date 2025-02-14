<script setup>
import Piano from './components/Piano.vue'
import Screen from './components/Screen.vue'
import Category from './components/Category.vue'
import Works from './components/Works.vue'
import Icons from './components/Icons.vue'
import Skills from './components/Skills.vue'
import Avatar from './components/Avatar.vue'
</script>

<template>
  <header>
    <div class="headwrap">
      <div class="name">
        <p>I'm</p>
        <p>EDOUARD</p>
        <p class="rav stroke anim-slide">rav<span class="dot">.</span></p>
      </div>
      <div class="hi">
        <h1 class="anim-raise">Hi!</h1>
        <div class="flex">
          <div class="frames">
            <Screen color="white" />
            <Piano />
          </div>
          <p class="role">pianist & <br>web developer</p>
        </div>
      </div>
    </div>
  </header>
  <div class="content">
    <Category class="me">
      <div class="me-wrap">
        <Avatar />
        <div class="presentation">
          <p>I play <strong>jazz</strong> and I build <strong>web apps</strong> with</p>
          <div class="techs">
            <strong>ruby on rails</strong>
            <strong class="tab">vue.js</strong>
            <strong>three.js</strong>
          </div>
          <p class="tab">I can't keep my hands off of <strong>keyboards</strong>.</p>
        </div>
      </div>
    </Category>
    <Category title="skills">
      <Skills />
    </Category>
    <Category title="works">
      <Works />
    </Category>
    <Category class="contact" title="contact">
      <div class="center">
        <p>You feel like <strong>building</strong> something <strong>amazing?</strong> 🔥</p>
        <p>Feel free to contact me :</p>
        <p class="contact-info">edravelo@gmail.com</p>
        <Icons />
      </div>
    </Category>
  </div>
</template>

<style scoped>
.contact {
  .center {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
  }
}

.role {
  font-family: 'CabinetGrotesk-ExtraBold';
  text-shadow: -3px 4px 0px var(--darker-green);
}

.content {
  border-radius: 0 0 10px 0;
  overflow: hidden;
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

  .me-wrap {
    display: flex;
    align-items: center;
  }

  .presentation {

    p {
      margin: 0 5px;
    }

    .techs {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 5px;
      margin: 20px;

      .tab {
        margin-left: 8px;
      }
    }

  }
}

.contact {
  padding-bottom: 70px;
}
</style>
