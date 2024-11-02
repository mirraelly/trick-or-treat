<script scoped>

import 'animate.css';
import lottie from "lottie-web";
import GameInstructions from './derived/GameInstructions.vue';

export default {
  nome: "Mural",
  components: {
    GameInstructions
  },
  props: {
    animationPath: {
      type: String,
      required: true,
    },
    GameInstructions: {
      type: String,
      required: true
    }
  },
  mounted() {
    lottie.loadAnimation({
      container: this.$refs.lottieContainer,
      renderer: "svg",
      loop: true,
      autoplay: true,
      path: this.animationPath,
    });
  },
  data() {
    return {
      showFirstContainer: true,
    }
  },
  methods: {
    startGame() {
      this.showFirstContainer = false; 
    }
  }
}
</script>

<template>
  <section v-if="showFirstContainer" class="container first-container">
    <h1 class="title animate__animated animate__bounceIn animate__infinite">Trick or Treat?</h1>
    <button class="init" @click="startGame">START</button>
  </section>
  <section v-else class="second-container">
    <GameInstructions @name-submitted="$emit('nameSubmitted', $event)" />
  </section>
</template>

<!-- // import { ref, onMounted } from 'vue';
// const count = ref(0)

// function increment() {
//   count.value++
// }

// onMounted(() => {
//   console.log(`The initial count is ${count.value}.`)
// }) -->

<!-- <template>
  <button @click="increment" class="init">START {{ count }}</button>
        <div ref="lottieContainer" style="width: 300px; height: 300px;">
          <DotLottieVue style="height: 500px; width: 500px" autoplay loop
            src="https://lottie.host/embed/723b6dd1-9703-4a02-b78a-158877080366/NN1yxzKJKO.json" />
        </div>
      </template> -->
<style>
.container {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  flex-direction: column;
  animation-fill-mode: both;
}

.title {
  margin: 5rem auto 3rem auto;
  animation-duration: 2s;
}

.init {
  background-color: #FFA726;
  padding: 1rem 3rem;
  border-radius: 0.5rem;
  color: #FFFFFF;
  font-size: 2rem;
  font-weight: 800;
  -webkit-text-stroke-width: 1.5px;
  -webkit-text-stroke-color: #000;
  box-shadow: 0 4px 5px 3px #000000b0 !important;
}

/* .second-container {
  display: none;
} */
</style>
