<template>
  <div>
    <input v-model="text" />
    <p>{{ text }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: "",
    };
  },
  methods: {
    wowie() {
      console.log("amongus");
    },
  },
};
</script>

<style lang="scss" scoped></style>
