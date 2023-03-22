<script setup>
import { viewDepthKey } from "vue-router";
import wowow from "../components/wowow.vue";
import { ref, onMounted } from "vue";

let hats = ref([
  {
    name: "Amongus - 2bucks",
    img: "https://1.bp.blogspot.com/-C4pbViQnphU/YEXEf-4fQ6I/AAAAAAAAYA8/8cfFY-lITvwcrvyZfgc7krR9A_vJY0IPACLcBGAsYHQ/s16000/AmongUs-Hat-Final.jpg",
  },
  {
    name: "Hats (plural)",
    img: "https://wiki.teamfortress.com/w/images/thumb/f/f5/Towering_Pillar_of_Hats.png/250px-Towering_Pillar_of_Hats.png",
  },
]);
function test() {
  console.log(hats);
}
test();
</script>

<template>
  <div ref="div">
    <wowow>
      <template #title> amongus</template>
      <template #img>
        <img
          src="https://1.bp.blogspot.com/-C4pbViQnphU/YEXEf-4fQ6I/AAAAAAAAYA8/8cfFY-lITvwcrvyZfgc7krR9A_vJY0IPACLcBGAsYHQ/s16000/AmongUs-Hat-Final.jpg"
        />
      </template>
    </wowow>
    <wowow>
      <template #title> Hats (plural) </template>
      <template #img>
        <img
          src="https://wiki.teamfortress.com/w/images/thumb/f/f5/Towering_Pillar_of_Hats.png/250px-Towering_Pillar_of_Hats.png"
        />
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
