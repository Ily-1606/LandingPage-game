<template>
  <div class="fixed top-0 left-0 right-0 p-4 bg-blue-300 z-50">
    <div class="float-right text-white align-middle space-x-4 cursor-pointer">
      <user-svg class="w-10 h-10 inline-block " />
      <div class="inline-block">Đăng nhập</div>
    </div>
  </div>
</template>
<script>
import userSvg from "../assets/images/svgs/user.svg?component";
export default {
  components: {
    userSvg,
  },
};
</script>
