<template>
  <div class="home flex-grow-1 d-flex flex-column align-items-center justify-content-center">
    <div class="home-card p-5 bg-white rounded elevation-3">
      <div class="btn selectable selectable-none" @click="slash">
        <img src="https://pixeljoint.com/files/icons/full/skell1.gif" alt="CodeWorks Logo"
        draggable="false" class="rounded-circle monster unselectable">
        <img class="slash" v-if="toggle" draggable="false" src="https://thumbs.gfycat.com/AridDigitalGibbon-max-1mb.gif"
          alt="CodeWorks Logo">
      </div>
      <h1 class="my-5 bg-dark text-white p-3 rounded text-center">
        Vue 3 Starter
      </h1>
    </div>
  </div>
</template>

<script>
import { computed } from "@vue/reactivity";
import { AppState } from "../AppState.js";


export default {
  name: 'Home',
  setup() {
    return {
      toggle: computed(() => AppState.toggle),
      slash() {
        console.log('slash!');
        AppState.toggle = !AppState.toggle
        setTimeout(() => AppState.toggle = false, 300);
      }
    }
  }

}
</script>

<style scoped lang="scss">
.home {
  display: grid;
  height: 80vh;
  place-content: center;
  text-align: center;
  user-select: none;

  .home-card {
    width: 50vw;

    .slash {
      position: absolute;
      width: 200px;
      right: 0px;
      -webkit-user-drag: none;
      user-select: none;
      -moz-user-select: none;
      -webkit-user-select: none;
      -ms-user-select: none;
    }

    .monster {
      position: relative;
      -webkit-user-drag: none;
      user-select: none;
      -moz-user-select: none;
      -webkit-user-select: none;
      -ms-user-select: none;
    }

    >img {
      height: 200px;
      max-width: 200px;
      width: 100%;
      object-fit: contain;
      object-position: center;
    }
  }
}
</style>
