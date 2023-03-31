<script setup>
import { viewDepthKey } from "vue-router";
import wowow from "../components/wowow.vue";
import { ref, onMounted, defineProps } from "vue";

let cart = ref([]);
let cart_prices = ref([]);
let cart_prices_int = ref(0);
let cart_prices_sub = ref([]);
let cart_prices_sub_int = ref(0);
let cart_total = ref(0);

function removeItem(array) {
  console.log(array);
  cart_prices_sub.value.push(array);
  let sum = ref(0);
  cart_prices_sub.value.forEach((element) => (sum.value += element));
  console.log(sum.value);
  cart_prices_sub_int.value = sum.value;
  cart_total.value = cart_prices_int.value - cart_prices_sub_int.value;
}

function cartValue(array) {
  console.log(array);
  cart_prices.value.push(array);
  console.log(cart_prices.value);
  let sum = ref(0);
  cart_prices.value.forEach((element) => (sum.value += element));
  cart_prices_int.value = sum.value;
  cart_total.value = cart_prices_int.value - cart_prices_sub_int.value;
}
const hats = ref([
  {
    name: "Amongus - 2bucks",
    img: `https://1.bp.blogspot.com/-C4pbViQnphU/YEXEf-4fQ6I/AAAAAAAAYA8/8cfFY-lITvwcrvyZfgc7krR9A_vJY0IPACLcBGAsYHQ/s16000/AmongUs-Hat-Final.jpg`,
    price: 3,
    shown: true,
  },
  {
    name: "Hats (plural) - 5 buckx",
    img: `https://wiki.teamfortress.com/w/images/thumb/f/f5/Towering_Pillar_of_Hats.png/250px-Towering_Pillar_of_Hats.png`,
    price: 5,
    shown: true,
  },
]);

function test(x) {
  console.log(x.name);
  cart.push(x.price);
}
</script>

<template>
  <p>total cart value: {{ cart_total }}</p>
  <div v-for="hat in hats" id="susdiv1">
    <wowow>
      <template #title>{{ hat.name }}</template>
      <template #img>
        <img v-bind:src="hat.img" />
      </template>
      <template #button>
        <button
          v-if="hat.shown"
          @click="cartValue(hat.price), (hat.shown = !hat.shown)"
        >
          buy this item
        </button>
        <button v-else @click="removeItem(hat.price), (hat.shown = !hat.shown)">
          remove from cart
        </button>
      </template>
    </wowow>
  </div>
</template>

<style lang="scss" scoped>
div {
  display: flex;
  justify-content: center;
  align-content: horizontal;
  flex-wrap: wrap;
  margin: 20px;
}

img {
  height: 250px;
  width: 200px;
}

p {
  text-align: center;
}
</style>
