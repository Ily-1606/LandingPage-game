<template>
  <div class="relative" style="height: 1578px">
    <div class="bg-background absolute inset-0 space-y-10 -z-10"></div>
    <div class="cont mx-auto space-y-8">
      <div class="text-6xl font-bold text-center text-slate-200">
        Characters
      </div>
      <div class="relative">
        <div class="grid grid-cols-2 thumbs absolute z-50">
          <div v-for="(character, index) in ['woody','lucy','bambi', 'speck','bubbles', 'biff', 'uba', 'popi']" :key="character" class="cursor-pointer" @click="setSlider(index)" :class="[currentCharacter === index ? 'thumb_active' : '', character]"></div>
        </div>
        <slider-character @onSlideChange="onSlideChange" :currentCharacter="currentCharacter"></slider-character>
      </div>
    </div>
  </div>
</template>
<style scoped>
.bg-background {
  background-image: url("../../assets/images/bg-character.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 50% 50%;
  width: 100%;
  height: 100%;
}
.thumbs {
  top: 150px;
  left: 50px;
}
.thumbs > * {
  width: 118px;
  height: 118px;
  margin-bottom: 30px;
  background: url('../../assets/images/characters/list.png')
    no-repeat 0 0;
}
.thumbs > *.thumb_active{
    background-position-x: -135px;
}
.lucy {
  background-position-y: -552px;
}
.speck {
  background-position-y: -690px;
}
.bambi {
  background-position-y: -138px;
}
.bubbles {
  background-position-y: -276px;
}
.biff {
  background-position-y: -828px;
}
.uba{
    background-position-y: -414px;
}
.popi{
    background-position-y: -966px;
}
.cont {
  padding-top: 200px;
  height: 100%;
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
.leading-12 {
  line-height: 50px;
}
</style>
<script>
import SliderCharacter from "../SliderCharacter.vue";
export default {
  components: { SliderCharacter },
  data() {
    return {
      currentCharacter: 0,
    };
  },
  methods: {
    onSlideChange(index){
      this.currentCharacter = index;
    },
    setSlider(index){
      this.currentCharacter = index;
    }
  },
};
</script>
