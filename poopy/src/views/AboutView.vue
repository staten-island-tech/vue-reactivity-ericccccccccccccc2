<script setup>
import { viewDepthKey } from "vue-router";
import wowow from "../components/wowow.vue";
import { ref, onMounted, defineProps } from "vue";

const wow = defineProps(true);
let cart = ref([]);
let cart_prices = ref([]);
const div = ref(null);
let amongus = "wow";
let cart_total = ref(0);

function removeItem(x) {
  wow.value = !wow.value;
}

function cartValue(array) {
  wow.value = !wow.value;
  console.log(array);
  cart_prices.value.push(array);
  console.log(cart_prices.value);
  let sum = ref(0);
  cart_prices.value.forEach((element) => (sum.value += element));
  cart_total.value = sum.value;
}
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
  <p>total cart value: {{ cart_total }}</p>
  <div v-for="hat in hats" id="susdiv1">
    <wowow>
      <template #title>{{ hat.name }}</template>
      <template #img>
        <img v-bind:src="hat.img" />
      </template>
      <template #button>
        <button v-if="wow" @click="cartValue(hat.price)">buy this item</button>
        <button v-else @click="removeItem(hat.price)">test</button>
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

p {
  text-align: center;
}
</style>

https://sfc.vuejs.org/#eNp9Uk1v2zAM/SuEMMApFlvLtpPhBN2A7jagwIDtUO+QOLSj1JYESU7nGf7vo/wRp2tTn8z3Hh8pki37onV0qpHFLLGZEdqBRVfrTSpFpZVx0ILBHDrIjaogIGlwpr6WqrhX1o1cxCfAO5IMIJWZkiTQBFpYe6vFgydaEPsYVktwwpUYQ/C9gaOqjcQGnoQ7wE9ygG45az/OWl+mELK4ovw0K38dGs+DsGAV5LUkZSp/36TysrNvSrof4i+ODa6ITvgwDZoDBQ4rXW4d+sgle3GC2LqmxHXKWsjH7Pi513sIsPLlGGUBfck0nSEEOIW5MmTh00DIYUgpm+j4EZuRjcT+Au8fNzF9MJO3KMutKTB0+MeNmrmlNXyIVpN4k5z31XeYcHoY/SX8/Fy2ZMOqw2qro6NVku6k7Rc7EtRvDD3iMVq7j1N2cE7bmHObZ/4WjjZSpuD0F5laOlFhhLYKd0Y9WTRknLJ+f6MHJ/CEJjQo92jQvOX5n/SFr7ellXf0lMvrfOXe95gLifdGabt4CPq5Bv5SBvyuEs7jl/Pt6auXQhP1l5KVW2tpEzuqHvp1zAdx+Lxp2+FWoesSTvHI7GrnlITbrBTZIyW/Qyq/eF78hozuBgA8kPAh6+oyu3+/5lNs
