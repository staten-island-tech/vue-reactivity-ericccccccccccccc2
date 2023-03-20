<script setup>
import { RouterView } from "vue-router";
</script>

<template>
  <div>
    <div class="wrapper">
      <h1>Hat Shop</h1>
    </div>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Store</RouterLink>
        <RouterLink to="/about">items</RouterLink>
        <RouterLink to="/amongus">asdfads</RouterLink>
      </nav>
    </div>

    <RouterView />
  </div>
</template>

<style lang="scss" scoped>
div {
  display: flex;
  place-items: flex-start;
  flex-wrap: wrap;
  padding: 10px;
}
</style>
