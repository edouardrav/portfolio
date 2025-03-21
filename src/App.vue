<script setup>
import { onMounted, useTemplateRef } from 'vue'
import Piano from './components/Piano.vue'
import Screen from './components/Screen.vue'
import Category from './components/Category.vue'
import Works from './components/Works.vue'
import Icons from './components/Icons.vue'
import Skills from './components/Skills.vue'
import Avatar from './components/Avatar.vue'
import ScrollHelper from './components/ScrollHelper.vue'

const content = useTemplateRef('content')
const scrollHelper = useTemplateRef('scrollHelper')
let resizeObserver = null

onMounted(() => {
  updateContentPosition()

  resizeObserver = new ResizeObserver(entries => {
    for (const entry of entries) {
      updateContentPosition()
    }
  })
  resizeObserver.observe(content.value)
})

window.addEventListener('resize', () => {
  updateContentPosition()
})

const updateContentPosition = () => {
  const contentMarginBottom = parseFloat(getComputedStyle(document.documentElement).getPropertyValue('--content-margin-bottom'));
  console.log(contentMarginBottom)
  const result = (content.value.offsetHeight - window.innerHeight) * 1.05 + contentMarginBottom
  document.querySelector(':root').style.setProperty('--content-translate-y', `-${result}px`)
  scrollHelper.value.updateContentTransform()
}
</script>

<template>
  <ScrollHelper ref="scrollHelper" />
  <header class="header-anim">
    <div class="header-bg header-bg-anim">
    </div>
    <div class="little-frames little-frames-anim">
      <Screen color="white" />
      <Piano />
    </div>
    <div class="headwrap">
      <div class="name name-anim">
        <p class="im-anim">I'm</p>
        <p class="edouard-anim">EDOUARD</p>
        <div class="rav-wrap rav-anim">
          <p class="rav stroke anim-slide">rav<span class="dot">.</span></p>
        </div>
      </div>
      <div class="hi hi-anim">
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
  <div class="content content-anim" ref="content">
    <Category class="me">
      <div class="me-wrap">
        <Avatar />
        <div class="presentation">
          <p>I play jazz and I build <strong>web apps</strong> with</p>
          <div class="techs">
            <strong>ruby on rails</strong>
            <strong class="vue">vue.js</strong>
            <strong class="three">three.js</strong>
          </div>
        </div>
      </div>
      <p class="underline">I can't keep my hands off of <strong>keyboards</strong>.</p>
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
  <div class="scrollable">
  </div>
</template>

<style scoped>
.scrollable {
  height: calc(1.5 * var(--content-height));
}

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

/* DESKTOP */
@media (min-width: 992px) {
  .content {
    width: 780px;
    margin-left: 360px;
    margin-top: 130px;
  }
}
/* TABLET */
@media (min-width: 576px) and (max-width: 992px) {
  .content {
    width: calc(100% - 80px);
    margin-top: 120px;
    margin-bottom: 100px;
  }
}
/* MOBILE */
@media (max-width: 576px) {
  .content {
    width: calc(100% - 20px);
    margin-top: 50px;
    margin-bottom: 50px;
  }
}

.content {
  border: 1px solid #aaa;
  box-shadow: -3px 3px 3px #00000022;
  position: fixed;
  border-radius: 0 0 10px 10px;
  overflow: hidden;
  background-color: #ffffffaa;
  padding-top: 200px;
  display: flex;
  flex-direction: column;
  gap: 8px;

  p {
    font-size: 1em;
  }

  strong {
    font-family: 'CabinetGrotesk-Bold';
    /*font-family: 'iAQuattro-Bold';*/
    color: var(--charcoal);
    font-size: 1.3em;
    font-weight: 700;
  }

  .me {
    display: flex;
    justify-content: center;


    @media (min-width: 576px) {
      .underline {
        margin-left: 40px;
      }

      .me-wrap {
        align-items: flex-end;
      }
    }

    @media (max-width: 576px) {
      .me-wrap {
        align-items: flex-start;
      }
    }

    .me-wrap {
      display: flex;
      gap: 30px;

      .presentation {

        .techs {
          display: flex;
          flex-direction: column;
          align-items: flex-start;
          gap: 5px;

          @media (min-width: 576px) {
            margin-top: 20px;
          margin-bottom: 0;
          }

          @media (max-width: 576px) {
            margin-top: 50px;
          margin-bottom: 20px;
          }


          .vue {
            @media (min-width: 576px) {
              margin-left: -10px;
            }

            @media (max-width: 576px) {
              margin-left: -20px;
            }
          }

          .three {
            @media (min-width: 576px) {
              margin-left: -25px;
            }

            @media (max-width: 576px) {
              margin-left: -45px;
            }
          }
        }
      }
    }
  }
}

.contact {
  padding-bottom: 70px;
}
</style>
