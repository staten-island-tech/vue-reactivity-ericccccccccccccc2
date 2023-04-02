<script setup>
import { RouterView } from "vue-router";
</script>

<template>

    <div class="title">
      <h1>Hat Shop</h1>
    </div>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">About Us &nbsp</RouterLink>
        <RouterLink to="/about">Shop &nbsp</RouterLink>
        <RouterLink to="/amongus">Cart &nbsp</RouterLink>
      </nav>
    </div>

    <RouterView />

</template>

<style lang="scss" scoped>
.title {
  text-align: center;
  font-size: 50px;
}
.wrapper {
  text-align: center;
  margin: 20px;
}

nav {
  font-size: 20px;
}

</style>
