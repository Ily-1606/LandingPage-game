<template>
  <div>
    <img :src="dataItem.image" />
    <div class="space-x-6 flex text-xl justify-center content-center">
      <div class="border-pets text-center">Type</div>
      <div class="text-center def font-bold">{{dataItem.type}}</div>
    </div>
    <div class="space-x-4 text-2xl my-8 w-full">
        <span class="tag" v-for="tag in dataItem.tags" :key="tag">{{tag}}</span>
    </div>
  </div>
</template>
<style scoped>
.border-pets {
  background-image: url("../../../assets/images/border.png");
  background-repeat: no-repeat;
  background-size: cover;
  width: 118px;
  height: 43px;
  margin-right: 20px;
  color: #f3edcd;
  font-size: 24px;
  line-height: 43px;
}
.def {
  font-size: 36px;
  color: #5c362c;
  letter-spacing: -0.025em;
}
.tag{
    color: #8c4525;
    display: inline-block;
}
</style>
<script>
export default {
    props: {
        dataItem: {
            type: Object,
            required: true
        }
    }
}
</script>
