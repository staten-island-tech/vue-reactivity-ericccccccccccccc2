<script setup>
import wowow from "../components/wowow.vue";
</script>

<template>
  <div>
    <wowow>
      <template #title> Amongus </template>
      <template #img>
        <img
          src="https://assets.nintendo.com/image/upload/f_auto/q_auto/dpr_2.0/c_scale,w_400/ncom/en_US/games/switch/a/among-us-switch/description-image"
        />
      </template>
    </wowow>
  </div>
</template>

<style lang="scss" scoped>
div {
  display: flex;
  justify-content: center;
  align-content: vertical;
  flex-wrap: wrap;
}
</style>
