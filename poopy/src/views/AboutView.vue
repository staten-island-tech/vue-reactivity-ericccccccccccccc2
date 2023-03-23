<script setup>
import { viewDepthKey } from "vue-router";
import wowow from "../components/wowow.vue";
import { ref, onMounted } from "vue";

const div = ref(null);

const hats = ref([
  {
    name: "Amongus - 2bucks",
    img: `"https://1.bp.blogspot.com/-C4pbViQnphU/YEXEf-4fQ6I/AAAAAAAAYA8/8cfFY-lITvwcrvyZfgc7krR9A_vJY0IPACLcBGAsYHQ/s16000/AmongUs-Hat-Final.jpg"`,
  },
  {
    name: "Hats (plural)",
    img: `https://wiki.teamfortress.com/w/images/thumb/f/f5/Towering_Pillar_of_Hats.png/250px-Towering_Pillar_of_Hats.png"`,
  },
]);

function test() {
  div.value.textcontent = "";
}
onMounted(() => {
  test();
});
</script>

<template>
  <div v-for="hat in hats" id="susdiv1">
    <wowow>
      <template #title>{{ hat.name }}</template>
      <template #img>
        {{ hat.img }}
      </template>
    </wowow>
  </div>
  <button @click="console.log(hats)">test</button>
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
