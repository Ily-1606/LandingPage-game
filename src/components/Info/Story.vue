<template>
  <div class="relative" style="height: 1857px">
    <div class="bg-background absolute inset-0 space-y-10 -z-10"></div>
    <div class="cont mx-auto space-y-8">
      <div class="text-6xl font-bold text-center text-slate-500">
        StoneAge World History
      </div>
      <div class="text-center text-white text-3xl">
        Let me tell you the origins of StoneAge World.
      </div>
      <div class="learn_more mx-auto cursor-pointer" @click="toogleModal">
        <div class="text-3xl text-slate-500 font-bold pt-12 text-center">
          Click to learn more!
        </div>
      </div>
      <slider :data-slider="sliderData"  />
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
  background-image: url("../../assets/images/bg-story.jpg");
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
</style>
<script>
import Slider from "../Slider.vue";
import Modal from "../Modal.vue";
export default {
  components: { Slider, Modal },
  data() {
    return {
      showModal: false,
      APP_TRAILER: import.meta.env.VITE_APP_STORY_TRAILER,
      sliderData: [{
          title: ["StoneAge returns as an","unprecedented mobile","MMORPG"],
          hightLight: 2,
          desc: ["Meet colorful NPCs and","explore the world of StoneAge","with prehistoric pets."]
      },{
          title: ["Now you can go on","adventures with friends","in this", "prehistoric world."],
          hightLight: 3,
          desc: ["Meet colorful NPCs and","explore the world of StoneAge","with prehistoric pets."],
      },{
          title: ["Don't forget","about searching for","rare pets", "in Tectonika."],
          hightLight: 3,
          desc: ["Become the best trainer and","learn all of StoneAge World’s","secrets."],
      }]
    };
  },
  methods: {
    toogleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>
