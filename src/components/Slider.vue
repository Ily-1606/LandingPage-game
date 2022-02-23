<template>
  <div>
    <swiper
      :spaceBetween="30"
      :centeredSlides="true"
 
      :pagination="{
        clickable: true,
      }"
      :navigation="true"
      :modules="modules"
      class="mySwiper"
    >
        <swiper-slide v-for="(row, index) in dataSlider" :key="index" class="text-white text-5xl text-center space-y-4">
          <p v-for="(title,indexTitle) in row.title" :key="title" :class="indexTitle === row.hightLight ? 'text-yellow-500' : ''">{{title}}</p>
          <div class="text-3xl" style="margin-top: 100px">
              <p v-for="(desc) in row.desc" :key="desc" >{{desc}}</p>
          </div>
        </swiper-slide>
    </swiper>
  </div>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay, Pagination, Navigation } from "swiper";
import "swiper/css";
import "swiper/css/pagination";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  props: {
    dataSlider: {
      type: Array,
      required: true
    }
  },
  data(){
      return {
           modules: [Autoplay, Pagination, Navigation],
      }
  }
};
</script>
<style>
.swiper-button-next, .swiper-button-prev{
    position: absolute;
    width: 90px;
    height: 90px;
    background: url('../assets/images/bg-controller-slide.png') no-repeat 0 0;
    z-index: 10;
}
.swiper-button-prev{
    left: 40px;
}
.swiper-button-next{
    right: 40px;
    background-position-x: -90px;
}
.swiper-button-next:after, .swiper-button-prev:after {
    display: block;
    content: "";
}
.swiper{
    position: relative;
    min-height: 840px;
}
.swiper-slide {
    padding: 0 140px;
}
.swiper-pagination-bullet{
    background: url('../assets/images/current-dot.png');
    border-radius: 0;
    opacity: 1;
    width: 20px;
    height: 57px;
    margin-left: 20px!important;
}
.swiper-pagination-bullet-active{
    width: 24px;
    background-position: 100% 0;
}
</style>