<template>
    <div class="download_area space-x-4 flex mx-auto justify-center">
        <a :href="GOOGLE_PLAY_URL_APP" class="download_google_play" target="_blank"></a>
        <a :href="APP_STORE_URL_APP" class="download_app_store" target="_blank"></a>
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
</style>
<script>
export default {
  data() {
    return {
      GOOGLE_PLAY_URL_APP: import.meta.env.VITE_GOOGLE_PLAY_URL_APP,
      APP_STORE_URL_APP: import.meta.env.VITE_APP_STORE_URL_APP,
    };
  },
}
</script>