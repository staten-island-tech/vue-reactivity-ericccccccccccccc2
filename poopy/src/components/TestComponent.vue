<template>
  <h3><slot name="title"></slot></h3>
  <slot name="img"></slot>
  <h4><slot name="price"></slot></h4>
  <button>buy this item</button>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
div {
  display: flex;
  justify-content: center;
  flex-direction: column;
  text-align: center;
  height: 300px;
  width: 300px;
}

img {
  height: 20px;
  width: 30px;
}
</style>
