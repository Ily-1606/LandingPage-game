<template>
  <swiper
    :spaceBetween="30"
    :centeredSlides="true"
    :initialSlide="currentPet"
    :navigation="true"
    :modules="modules"
    class="mySwiper"
    @slideChange="onSlideChange"
    @swiper="swiper"
    ref="character_swipper"
  >
    <swiper-slide>
      <div class="text-white font-bold text-5xl text-center mt-4">Woody</div>
      <img class="ml-32 mt-10" src="../assets/images/characters/Woody.png" />
      <div class="des text-center">“I can be indecisive but I’m loveable.”</div>
    </swiper-slide>
    <swiper-slide>
      <div class="text-white font-bold text-5xl text-center mt-4">Lucy</div>
      <img class="ml-32 mt-10" src="../assets/images/characters/Lucy.png" />
      <div class="des text-center">
        “I don’t know where I’m from, but I know where I’m going.”
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="text-white font-bold text-5xl text-center mt-4">Bambi</div>
      <img class="ml-32 mt-10" src="../assets/images/characters/Bambi.png" />
      <div class="des text-center">
        “I just happen to get along with everyone!”
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="text-white font-bold text-5xl text-center mt-4">Speck</div>
      <img class="ml-32 mt-10" src="../assets/images/characters/Speck.png" />
      <div class="des text-center">“Ask me anything about dinosaurs.”</div>
    </swiper-slide>
    <swiper-slide>
      <div class="text-white font-bold text-5xl text-center mt-4">Bubbles</div>
      <img class="ml-32 mt-10" src="../assets/images/characters/Bubbles.png" />
      <div class="des text-center">
        “If you make fun of my height, I’m going to headbutt you!”
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="text-white font-bold text-5xl text-center mt-4">Biff</div>
      <img class="ml-32 mt-10" src="../assets/images/characters/Biff.png" />
      <div class="des text-center">
        “I get the job done, and get it right the first time.”
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="text-white font-bold text-5xl text-center mt-4">Uba</div>
      <img class="ml-32 mt-10" src="../assets/images/characters/Uba.png" />
      <div class="des text-center">“My clothes? I crafted them carefully!”</div>
    </swiper-slide>
    <swiper-slide>
      <div class="text-white font-bold text-5xl text-center mt-4">Popi</div>
      <img class="ml-32 mt-10" src="../assets/images/characters/Popi.png" />
      <div class="des text-center">“I won’t pull any pranks. Honest!”</div>
    </swiper-slide>
  </swiper>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay, Navigation } from "swiper";
import "swiper/css";
import "swiper/css/pagination";
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  props: {
    currentCharacter: {
      type: Number,
      default() {
        return 0;
      },
    },
  },
  data() {
    return {
      modules: [Autoplay, Navigation],
      swipper: null
    };
  },
  watch: {
    currentCharacter() {
      this.swipper.slideTo(this.currentCharacter)
    },
  },
  emits: ["onSlideChange"],
  methods: {
    onSlideChange(e) {
      this.$emit("onSlideChange", e.activeIndex);
    },
    swiper(e){
      this.swipper = e
    }
  },
};
</script>
<style scoped>
.des {
  font-size: 50px;
  color: #ffcf29;
}
</style>
