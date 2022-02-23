<template>
  <div class="relative" style="height: 2198px;">
    <div class="bg-background absolute inset-0 space-y-10 -z-10"></div>
    <div class="cont mx-auto space-y-8">
      <div class="text-6xl font-bold text-center text-slate-200">
        Pet Habitats
      </div>
      <div class="flex space-x-14 justify-center">
        <div class="text-center cursor-pointer">
          <div
            class="map_btn map-crag mx-auto"
            :class="currentMap === 'crag' ? 'map-active' : ''"
            @click="setMap('crag')"
          ></div>
          <div class="text-white text-3xl font-bold">Crag Isle</div>
        </div>
        <div class="text-center cursor-pointer">
          <div
            class="map_btn map-jaru mx-auto"
            :class="currentMap === 'jaru' ? 'map-active' : ''"
            @click="setMap('jaru')"
          ></div>
          <div class="text-white text-3xl font-bold">Jaru Isle</div>
        </div>
        <div class="text-center cursor-pointer">
          <div
            class="map_btn map-gravelin mx-auto"
            :class="currentMap === 'gravelin' ? 'map-active' : ''"
            @click="setMap('gravelin')"
          ></div>
          <div class="text-white text-3xl font-bold">Gravelin Isle</div>
        </div>
      </div>
      <div>
        <crag-map v-if="currentMap === 'crag'" />
        <jaru-map v-if="currentMap === 'jaru'" />
        <gravelin-map v-if="currentMap === 'gravelin'" />
      </div>
      <div class="text-white text-3xl space-y-6 text-center">
        <p class="text-yellow-500">
          *The pet shown is the main pet image for that family.
        </p>
        <p class="leading-12">
          An island with grassy plains and a desert. There are 4 villages located
          on the island.
        </p>
        <p class="leading-12">
          In Shamgir Village, the largest of the four villages, stands a statue
          of Shamgir the Great. Its proximity to a meadow makes it a great place
          for both pets and people to live.
        </p>
        <p class="leading-12">
          The Priest who oversees The Paragon Trial resides in Kuo Village,
          which is near an Undersea Tunnel to Jaru Isle.
        </p>
        <p class="leading-12">
          You can find pets from the Peachpig, Cuekabit, Beachtoise, and Pino
          Families on Crag Isle.
        </p>
      </div>
    </div>
    <modal
      :show-modal="showModal"
      @toogle-modal="toogleModal"
      :url-embed="APP_TRAILER"
    />
  </div>
</template>
<style scoped>
.bg-background {
  background-image: url("../../assets/images/bg-map.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 50% 50%;
  width: 100%;
  height: 100%;
}
.learn_more {
  width: 371px;
  height: 480px;
  padding-right: 40px;
  background-image: url("../../assets/images/learn_more_story.png");
  background-repeat: no-repeat;
}
.cont {
  padding-top: 100px;
}
.map_btn {
  width: 140px;
  height: 150px;
  background-image: url("../../assets/images/list_map.png");
  background-repeat: no-repeat;
}
.map-crag.map-active,
.map-jaru.map-active,
.map-gravelin.map-active {
  background-position-y: -172px;
}
.map-jaru {
  background-position-x: -217px;
}
.map-gravelin {
  background-position-x: -434px;
}
.leading-12{
    line-height: 50px;
}
</style>
<script>
import CragMap from "../Maps/Crag.vue";
import JaruMap from "../Maps/Jaru.vue";
import GravelinMap from "../Maps/Gravelin.vue";
import Modal from "../Modal.vue";
export default {
  components: { Modal, CragMap, JaruMap, GravelinMap },
  data() {
    return {
      currentMap: "crag",
    };
  },
  methods: {
    toogleModal() {
      this.showModal = !this.showModal;
    },
    setMap(newMap) {
      this.currentMap = newMap;
    },
  },
};
</script>
