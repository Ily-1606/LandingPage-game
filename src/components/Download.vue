<template>
  <div>
    <div
      class="download_area space-x-4 flex mx-auto justify-center bottom-0 right-0 w-full p-2 z-50"
      ref="download"
    >
      <a
        :href="GOOGLE_PLAY_URL_APP"
        class="download_google_play"
        target="_blank"
      ></a>
      <a
        :href="APP_STORE_URL_APP"
        class="download_app_store"
        target="_blank"
      ></a>
    </div>
    <div
      v-if="!classData"
      class="download_area space-x-4 flex mx-auto justify-center bottom-0 right-0 w-full p-2 z-50 fixed_download"
    >
      <a
        :href="GOOGLE_PLAY_URL_APP"
        class="download_google_play"
        target="_blank"
      ></a>
      <a
        :href="APP_STORE_URL_APP"
        class="download_app_store"
        target="_blank"
      ></a>
    </div>
  </div>
</template>
<style scoped>
.download_area > a {
  background-size: auto;
  display: block;
  background-size: auto 69px;
  height: 69px;
}
.download_google_play {
  width: 233px;
  background: url("../assets/images/google_play.svg") no-repeat 0 0;
}
.download_app_store {
  width: 206px;
  background: url("../assets/images/en_appstore.svg") no-repeat 0 0;
}
.fixed_download {
  position: fixed;
  background-color: #433114;
}
</style>
<script>
export default {
  data() {
    return {
      GOOGLE_PLAY_URL_APP: import.meta.env.VITE_GOOGLE_PLAY_URL_APP,
      APP_STORE_URL_APP: import.meta.env.VITE_APP_STORE_URL_APP,
      classData: true,
    };
  },
  mounted() {
    window.onscroll = () => {
      this.classData = this.isScrolledIntoView();
    };
  },
  methods: {
    isScrolledIntoView() {
      const el = this.$refs.download;
      var rect = el.getBoundingClientRect();
      var elemTop = rect.top;
      var elemBottom = rect.bottom;
      var isVisible = elemTop >= 0 && elemBottom <= window.innerHeight;
      return isVisible;
    },
  },
};
</script>
