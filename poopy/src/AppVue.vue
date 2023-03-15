<script setup>
import TestComponent from "./components/TestComponent.vue";
</script>

<template>
  <div class="about">
    <p>test</p>
    <TestComponent>
      <template #title> Amongus </template>
      <template #img>
        <img
          src="https://assets.nintendo.com/image/upload/f_auto/q_auto/dpr_2.0/c_scale,w_400/ncom/en_US/games/switch/a/among-us-switch/description-image"
        />
      </template>
    </TestComponent>
    <WelcomeItemVue></WelcomeItemVue>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

img {
  height: 200px;
  width: 150px;
}

div {
  display: flex;
  justify-content: center;
  text-align: center;
  flex-direction: column;
  height: 300px;
  width: 150px;
}
</style>
