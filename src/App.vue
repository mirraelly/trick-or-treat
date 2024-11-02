<script setup>
import AppFooter from './components/AppFooter.vue';
import AppHeader from './components/AppHeader.vue';
import Mural from './components/Mural.vue';
import spiderWithWeb from '@/assets/images/spider-with-web.png';
import batMoon from '@/assets/images/bat-moon.png';
import witchFlying from '@/assets/images/witch-flying.png';
import 'animate.css';
import { ref } from 'vue';

const userName = ref('visitante');
const updateName = (name) => {
  userName.value = name;
}

</script>

<template>
  <div class="app">
    <AppHeader :userName="userName" :candyCount="candyCount" :trickCount="trickCount" />
    <main>
      <Mural @name-submitted="updateName" />
    </main>
    <AppFooter />
  </div>
  <div>
    <span class="backgroud-spider-with-web">
      <img :src="spiderWithWeb" alt="Spider With Web" class="spider-with-web" />
    </span>
    <span class="backgroud-bat-moon">
      <img :src="batMoon" alt="Bat and Moon" class="bat-moon" />
    </span>
    <span class="backgroud-witch-flying">
      <img :src="witchFlying" alt="Witch flying" class="witch-flying animate__animated animate__lightSpeedInLeft" />
    </span>
  </div>
</template>

<style scoped>
.app {
  position: relative;
}

.backgroud-spider-with-web {
  position: absolute;
  top: 0;
  left: 50%;
  width: 50%;
  height: 50%;
  z-index: -1;
}

.spider-with-web {
  z-index: 0;
  width: 100%;
  height: auto;
}

.backgroud-bat-moon {
  position: absolute;
  top: 2.25rem;
  right: 70%;
  width: 36%;
  height: 87%;
  z-index: -2;
}

.bat-moon {
  z-index: 0;
  width: 80%;
  height: auto;
}

.backgroud-witch-flying {
  position: absolute;
  top: 25%;
  right: 48%;
  width: 18rem;
  height: auto;
  z-index: -1;
}

.witch-flying {
  z-index: 0;
  width: 100%;
  height: auto;
}

@media (min-width: 780px) {}
</style>
