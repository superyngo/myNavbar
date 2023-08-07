<script setup>
import {nextTick} from "vue";
const googleSheetsEnv = {
  sheetID: "1qiQk_cpa-2W26a3djoXJh_zR9Ay3CGphO01ceAf91zE",
  sheetName: "sheet1",
  APIKey: "AIzaSyC8gWabbSXXk0UME4f85TRgEo5JXoE2z4A",
};
const fetchData = (
  await (
    await fetch(
      `https://sheets.googleapis.com/v4/spreadsheets/${googleSheetsEnv.sheetID}/values/${googleSheetsEnv.sheetName}?alt=json&key=${googleSheetsEnv.APIKey}`
    )
  ).json()
).values;
const state = [];
for (let i = 1; i < fetchData.length; i++) {
  state.push({
    tag: fetchData[i][0],
    title: fetchData[i][1],
    link: fetchData[i][2],
  });
}

state.reverse();
</script>

<template>
  <div class="navbar">
    <ul class="navbar-nav">
      <component
        v-for="item of state"
        :is="item.tag"
        :key="item.title"
        class="itemli"
      >
        <a :href="item.link" class="item">
          {{ item.title }}
        </a>
      </component>
    </ul>
    <div id="copyright">© 2023 superyngo All Rights Reserved.</div>
  </div>
</template>

<style scoped>
.navbar {
  position: relative;
  .navbar-nav {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 1rem;
    justify-content: center;

    .itemli {
      list-style: none;
      .item {
        color: var(--font-color);
        cursor: pointer;
        background: none;
        border: none;
        font-weight: 500;
        text-decoration: underline;
      }
      .item:hover {
        text-decoration: none;
      }
    }
  }
}
</style>
