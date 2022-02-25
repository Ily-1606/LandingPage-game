<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HomePage from "./components/Home.vue";
import FeaturePage from "./components/Info/Feature.vue";
import StoryPage from "./components/Info/Story.vue";
import MapPage from "./components/Info/Map.vue";
import CharacterPage from "./components/Info/Character.vue";
import Header from './components/header.vue'
</script>

<template>
  <div>
    <Header />
    <home-page class="mt-16" />
    <feature-page />
    <story-page />
    <map-page />
    <character-page />
  </div>
</template>
<script>
export default {
  beforeMount() {
    this.handleResize();
    window.onresize = (e) => {
      this.handleResize();
    };
  },
  methods: {
    handleResize() {
      if (window.outerWidth <= 800) {
        if (!document.querySelector("#meta_viewport")) {
          const meta = document.createElement("meta");
          meta.setAttribute("name", "viewport");
          meta.setAttribute("content", "width=800, user-scalable=no");
          meta.setAttribute("id", "meta_viewport");
          document.querySelector("head").appendChild(meta);
        }
      } else {
        const meta = document.querySelector("#meta_viewport");
        if (meta) {
          meta.remove();
        }
      }
    }
  },
};
</script>
