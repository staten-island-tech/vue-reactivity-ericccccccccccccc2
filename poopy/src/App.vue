<script setup>
import { RouterView } from "vue-router";
</script>

<template>
  <div class="bigger_wrapper">
    <div class="title">
      <h1>Hat Shop</h1>
    </div>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">About Us </RouterLink>
        <RouterLink to="/about">Yes </RouterLink>
        <RouterLink to="/amongus">asdfads </RouterLink>
      </nav>
    </div>

    <RouterView />
  </div>
</template>

<style lang="scss" scoped>
.title {
  text-align: center;
}
.wrapper {
  text-align: center;
  margin: 10px;
}

.bigger_wrapper {
  height: 1080px;
  width: 1920px;
}
</style>
