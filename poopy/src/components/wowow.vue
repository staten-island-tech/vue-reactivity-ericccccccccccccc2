<script>
import { ref, defineProps } from "vue";
</script>

<template>
  <div>
    <h3><slot name="title"></slot></h3>
    <slot name="img"></slot>

    <h4><slot name="price"></slot></h4>
    <slot name="button">
      <button @click="wowie2">buy this item</button>
      <button @click="wowie">remove from cart</button>
    </slot>
  </div>
</template>

<style lang="scss" scoped>
div {
  justify-content: center;
  flex-direction: column;
  text-align: center;

  align-content: vertical;
}
</style>
