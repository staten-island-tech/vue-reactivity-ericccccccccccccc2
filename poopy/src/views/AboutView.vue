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

function removeCart(array) {
  let target = cart.value.indexOf(array);
  cart.value.splice(target, 1);
}

function addCart(array) {
  cart.value.push(array);
}

function removeItem(array) {
  cart_prices_sub.value.push(array);
  let sum = ref(0);
  cart_prices_sub.value.forEach((element) => (sum.value += element));
  cart_prices_sub_int.value = sum.value;
  cart_total.value = cart_prices_int.value - cart_prices_sub_int.value;
}

function cartValue(array) {
  cart_prices.value.push(array);
  let sum = ref(0);
  cart_prices.value.forEach((element) => (sum.value += element));
  cart_prices_int.value = sum.value;
  cart_total.value = cart_prices_int.value - cart_prices_sub_int.value;
}
const hats = ref([
  {
    name: "Amongus - 3 bucks",
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
  {
    name: "Cool hat - 60 dollars",
    img: "data:image/jpeg;base64,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",
    price: 60,
    shown: true,
  },
  {
    name: "satan's hat - four unborn children",
    img: "https://m.media-amazon.com/images/I/611p3xTl6zL._AC_UL320_.jpg",
    price: 4,
    shown: true,
  },
  {
    name: "horse hat - 14 money",
    img: "https://spirit.scene7.com/is/image/Spirit/01525864-a?$Detail$",
    price: 14,
    shown: true,
  },
  {
    name: "weeb hat - 13 waifus",
    img: "https://store.crunchyroll.com/on/demandware.static/-/Sites-crunchyroll-master-catalog/default/dw5fb31849/images/6910193336364-1-ripple-junction-hats-jojo-s-bizarre-adventure-logo-bucket-hat-31766508634156.jpg",
    price: 13,
    shown: true,
  },
  {
    name: "big hat - 32 USD",
    img: "http://cdn.shopify.com/s/files/1/0373/4021/7475/products/NogginBoss_2021-01.jpg?v=1645416745",
    price: 32,
    shown: true,
  },
  {
    name: "rat hat - 5 dolar",
    img: "https://cdn.shopify.com/s/files/1/0529/6976/7092/products/beaver-hat-animal-hat-foam-wild-animal-hat-foam-party-hats-right.jpg?v=1676747948",
    price: 5,
    shown: true,
  },
  {
    name: "ikea hat - 89 swedish fish",
    img: "http://cdn.shopify.com/s/files/1/0053/6422/0019/products/PIKEA_Bucket_Hat.jpg?v=1625575428",
    price: 89,
    shown: true,
  },
  {
    name: "boomer hat - 9$ + inflation",
    img: "https://ichef.bbci.co.uk/news/976/cpsprodpb/10ACD/production/_87510386_da837f81-30fb-4bb9-9d57-5222d47bcdab.jpg",
    price: 9,
    shown: true,
  },
  {
    name: "nerd hat - 73 republic credits",
    img: "https://images.halloweencostumes.com/products/66629/1-1/star-wars-the-child-novelty-hat.jpg",
    price: 73,
    shown: true,
  },
  {
    name: "hairless hat - 13 bald ppl",
    img: "https://townsquare.media/site/466/files/2021/11/attachment-Bald-Head.jpg?w=980&q=75",
    price: 13,
    shown: true,
  },
]);
</script>

<template>
  <h3>total cart value: {{ cart_total }} assorted currencies</h3>
  <div v-for="item in cart">
    <p>{{ item.name }}</p>
  </div>
  <div class="wrapper">
    <div v-for="hat in hats" id="susdiv1">
      <wowow>
        <template #title>{{ hat.name }}</template>
        <template #img>
          <img v-bind:src="hat.img" />
        </template>
        <template #button>
          <button
            v-if="hat.shown"
            @click="
              cartValue(hat.price), (hat.shown = !hat.shown), addCart(hat)
            "
          >
            buy this item
          </button>
          <button
            v-else
            @click="
              removeItem(hat.price), (hat.shown = !hat.shown), removeCart(hat)
            "
          >
            remove from cart
          </button>
        </template>
      </wowow>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.wrapper {
  width: 1000px;
  margin-left: 430px;
}

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

h3 {
  text-align: center;
  font-size: 30px;
}
p {
  text-align: center;
}
</style>
