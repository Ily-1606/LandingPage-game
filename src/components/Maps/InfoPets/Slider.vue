<template>
  <div class="slider-pets">
    <swiper
      :spaceBetween="30"
      :centeredSlides="true"
      :initialSlide="currentPet"
      :navigation="true"
      :modules="modules"
      class="mySwiper"
    >
        <swiper-slide v-for="(pet,index) in dataSlider" :key="index" class="text-white text-5xl text-center space-y-4">
          <slider-item :data-item="pet"  />
        </swiper-slide>
    </swiper>
  </div>
</template>
<script>
import SliderItem from './SliderItem.vue'
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay, Navigation } from "swiper";
import "swiper/css";
import "swiper/css/pagination";

export default {
  components: {
    Swiper,
    SwiperSlide,
    SliderItem
  },
  props: {
    dataSlider: {
      type: Array,
      required: true
    },
    currentPet: {
        type: Number,
        required: true
    }
  },
  data(){
      return {
           modules: [Autoplay, Navigation],
      }
  }
};
</script>
<style>
.slider-pets .swiper-button-next, .slider-pets .swiper-button-prev{
    background-image: url('../../../assets/images/bg-controller-pets.png');
    background-repeat: no-repeat;
    top: 200px;
}
.slider-pets .swiper{
    position: relative;
    min-height: unset;
}
</style>