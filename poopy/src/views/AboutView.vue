<script setup>
import { ref } from "vue";
const amongus = ref(0);
</script>

<template>
  <button @click="amongus++">test</button>
  <h1>{{ amongus }}</h1>
</template>

<style lang="scss" scoped></style>
