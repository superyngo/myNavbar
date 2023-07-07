<script setup>
const state = [
  {tag: "li", title: "To Do", link: "https://superyngo.github.io/to-do-list/"},
  {
    tag: "li",
    title: "To Do Renderer",
    link: "https://superyngo.github.io/to-do_list_with_renderer/",
  },
  {tag: "li", title: "Timer", link: "https://superyngo.github.io/timer_vue3/"},
  {
    tag: "li",
    title: "Notebook",
    link: "https://superyngo.github.io/EasyNotebook_Vue3/",
  },
  {
    tag: "li",
    title: "Bill Splitter",
    link: "https://superyngo.github.io/bill_splitter_vue3/",
  },
  {
    tag: "li",
    title: "Calender",
    link: "https://superyngo.github.io/calender_vue3/",
  },
  {
    tag: "li",
    title: "Weight Tracker",
    link: "https://superyngo.github.io/weight_tracker_Chart.js/",
  },
  {
    tag: "li",
    title: "All Countries Around The Map",
    link: "https://superyngo.github.io/countries_around_world/",
  },
  {
    tag: "li",
    title: "Taiwan Weather Report",
    link: "https://superyngo.github.io/Taiwan_weather_report/",
  },
  {
    tag: "li",
    title: "Badge Generator",
    link: "https://superyngo.github.io/badge_generator/",
  },
  {
    tag: "li",
    title: "Quasar Framework copycat",
    link: "https://superyngo.github.io/QuasarFrameworkcopycat/",
  },
  {
    tag: "li",
    title: "Color Picker",
    link: "https://superyngo.github.io/colorful_colour_picker/",
  },
  {
    tag: "li",
    title: "Travel Maker",
    link: "https://github.com/superyngo/Travel-Maker",
  },
];
console.log(state);
</script>

<template>
  <div class="navbar">
    <ul class="navbar-nav">
      <component
        v-for="item of state"
        :is="item.tag"
        class="item"
        :key="item.title"
      >
        <a :href="item.link">{{ item.title }}</a>
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

    .item {
      list-style: none;
    }
  }
}
</style>
