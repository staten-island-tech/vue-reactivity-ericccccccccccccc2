<script setup>
import { viewDepthKey } from "vue-router";
import wowow from "../components/wowow.vue";
import { ref, onMounted } from "vue";

let cart = [];
let cart_prices = [];
const div = ref(null);
let amongus = "wow";
const hats = ref([
  {
    name: "Amongus - 2bucks",
    img: `https://1.bp.blogspot.com/-C4pbViQnphU/YEXEf-4fQ6I/AAAAAAAAYA8/8cfFY-lITvwcrvyZfgc7krR9A_vJY0IPACLcBGAsYHQ/s16000/AmongUs-Hat-Final.jpg`,
    price: 3,
  },
  {
    name: "Hats (plural) - 5 buckx",
    img: `https://wiki.teamfortress.com/w/images/thumb/f/f5/Towering_Pillar_of_Hats.png/250px-Towering_Pillar_of_Hats.png`,
    price: 5,
  },
]);

function test(x) {
  console.log(x.name);
  cart.push(x.price);
}
</script>

<template>
  <div v-for="hat in hats" id="susdiv1">
    <wowow>
      <template #title>{{ hat.name }}</template>
      <template #img>
        <img v-bind:src="hat.img" />
      </template>
      <template #button>
        <button @click="test(hat)">buy this item</button>
      </template>
    </wowow>
  </div>

  <p>{{ amongus }}</p>
</template>

<style lang="scss" scoped>
div {
  display: flex;
  justify-content: center;
  align-content: vertical;
  flex-wrap: wrap;
  margin: 20px;
}

img {
  height: 250px;
  width: 200px;
}
</style>
