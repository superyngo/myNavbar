<script setup>
import {nextTick} from "vue";
const state = [
  {tag: "li", title: "To Do", link: "https://superyngo.github.io/to_do_list/"},
  {
    tag: "li",
    title: "To Do Renderer",
    link: "https://superyngo.github.io/to_do_list_with_renderer/",
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
    title: "Every Country Around The Map",
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
    link: "https://superyngo.github.io/quasar_framework_copycat/",
  },
  {
    tag: "li",
    title: "Color Picker",
    link: "https://superyngo.github.io/colorful_colour_picker/",
  },
  {
    tag: "li",
    title: "Travel Maker",
    link: "https://superyngo.github.io/Travel-Maker/",
  },
];
nextTick(() => {
  // Get a reference to the link element within the iframe
  const item = document.querySelectorAll(".item");

  // Add a click event listener to the link
  item.forEach((li) =>
    li.addEventListener("mousedown", function (event) {
      // Get the target URL from the link
      const targetUrl = li.dataset.link;

      // Check if the middle button is clicked (button value: 1)
      if (event.button === 1) {
        // Open the link in a new page
        window.open(targetUrl, "_blank");
      }

      if (event.button === 0) {
        // Open the link in a new page
        window.location.href = targetUrl;
      }

      // Scroll the parent page to the target URL
      // window.parent.location.href = targetUrl;
    })
  );
});
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
        <button :data-link="item.link" class="item">
          {{ item.title }}
        </button>
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
        cursor: pointer;
        background: none;
        border: none;
        font-weight: 500;
        color: #000118;
        text-decoration: underline;
      }
      .item:hover {
        color: #48494e;
        text-decoration: none;
      }
    }
  }
}
</style>
