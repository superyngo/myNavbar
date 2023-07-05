<script setup>
const state = [
  {tag: "li", title: "Travel Maker", link: "#"},
  {tag: "li", title: "Travel Maker", link: "#"},
  {tag: "li", title: "Travel Maker", link: "#"},
  {tag: "li", title: "Travel Maker", link: "#"},
  {tag: "li", title: "Travel Maker", link: "#"},
  {tag: "li", title: "Travel Maker", link: "#"},
];
</script>

<template>
  <div class="navbar">
    <ul class="navbar-nav">
      <component
        v-for="comp of state"
        :is="comp.tag"
        class="item"
        key="comp.title"
      >
        <a href="comp.link">{{ comp.title }} </a>
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
    gap: 0.5rem;
    justify-content: center;

    .item {
      list-style: none;
    }
  }
}
</style>
