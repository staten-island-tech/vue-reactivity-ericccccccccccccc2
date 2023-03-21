<template>
  <div>
    <h3><slot name="title"></slot></h3>
    <slot name="img"></slot>

    <h4><slot name="price"></slot></h4>
    <button>buy this item</button>
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
