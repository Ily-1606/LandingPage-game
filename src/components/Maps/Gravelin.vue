<template>
  <div class="map-wrapper relative">
    <div class="bg-map absolute inset-0 z-0"></div>
    <div class="bg-pets absolute inset-0 z-10"></div>
    <div class="bg-icon absolute inset-0 z-20"></div>
    <div class="btns-wrap">
      <button class="btn3-1"></button>
      <button class="btn3-2"></button>
      <button class="btn3-3"></button>
      <button class="btn3-4"></button>
      <button class="btn3-5"></button>
    </div>
  </div>
</template>
<style scoped>
.bg-map {
  width: 100%;
  height: 100%;
  background-image: url("../../assets/images/maps/gravelin.png");
  background-repeat: no-repeat;
}
.bg-pets {
  top: 0;
  left: 190px;
  width: 662px;
  height: 575px;
  background-image: url("../../assets/images/maps/gravelin-pets.png");
  background-repeat: no-repeat;
}
.bg-icon {
  top: 60px;
  left: 300px;
  width: 525px;
  height: 474px;
  background-image: url("../../assets/images/maps/gravelin-icon.png");
  background-repeat: no-repeat;
}
.map-wrapper {
  width: 1197px;
  height: 891px;
  margin: 50px 0 0 -145px;
}
.btn3-1 {
  top: 75px;
  left: 190px;
  width: 170px;
  height: 154px;
}
.btn3-2 {
  top: 0;
  left: 605px;
  width: 150px;
  height: 130px;
}
.btn3-3 {
  top: 220px;
  left: 560px;
  width: 130px;
  height: 105px;
}
.btn3-4 {
  top: 408px;
  left: 210px;
  width: 145px;
  height: 115px;
}
.btn3-5 {
  top: 395px;
  left: 655px;
  width: 160px;
  height: 130px;
}
</style>
