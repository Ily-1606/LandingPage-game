<template>
  <div class="relative w-full h-screen">
    <div class="bg-background absolute inset-0 space-y-10">
      <div class="bg-logo mt-10 mx-auto"></div>
      <div class="text-white text-7xl text-center font-bold des mx-auto">
        <p>New Continent Eden has been discovered!</p>
        <p>Let's go to Eden!</p>
      </div>
      <div class="mx-auto bg-play" @click="toogleModal"></div>
      <download />
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
  background-image: url("../assets/images/home.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}
.bg-logo {
  position: relative;
  width: 339px;
  height: 181px;
  background-image: url("../assets/images/logo.png");
}
.download_area {
  max-width: 800px;
}
.des {
  max-width: 800px;
  letter-spacing: -0.025em;
  line-height: 1.2;
}
</style>
<script>
import Download from "./Download.vue";
import Modal from "./Modal.vue";
export default {
  components: { Download, Modal },
  data() {
    return {
      APP_TRAILER: import.meta.env.VITE_APP_TRAILER,
      showModal: false,
    };
  },
  mounted() {
  },
  methods: {
    toogleModal() {
      this.showModal = !this.showModal;
    }
  },
};
</script>
