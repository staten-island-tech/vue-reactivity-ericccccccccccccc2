<script setup>
import PokemonTemplateVue from "../components/PokemonTemplate.vue";
import TheWelcome from "../components/TheWelcome.vue";
import PokemonTemplate from "../components/PokemonTemplate.vue";
</script>

<template>
  <div>
    {{ test }}
  </div>
</template>

<script>
export default {
  component: {
    test: PokemonTemplate,
  },
};
</script>

<style lang="scss" scoped></style>
