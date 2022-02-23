<template>
  <div class="map-wrapper relative">
    <div class="bg-map absolute inset-0 z-0"></div>
    <div class="bg-pets absolute inset-0 z-10"></div>
    <div class="bg-icon absolute inset-0 z-20"></div>
    <div class="btns-wrap">
      <button class="btn2-1"></button>
      <button class="btn2-2"></button>
      <button class="btn2-3"></button>
      <button class="btn2-5"></button>
      <button class="btn2-6"></button>
      <button class="btn2-7"></button>
      <button class="btn2-8"></button>
      <button class="btn2-9"></button>
    </div>
  </div>
</template>
<style scoped>
.bg-map {
  width: 100%;
  height: 100%;
  background-image: url("../../assets/images/maps/jaru.png");
  background-repeat: no-repeat;
}
.bg-pets {
  top: 15px;
  left: 110px;
  width: 675px;
  height: 761px;
  background-image: url("../../assets/images/maps/jaru-pets.png");
  background-repeat: no-repeat;
}
.bg-icon {
  top: 30px;
  left: 190px;
  width: 603px;
  height: 687px;
  background-image: url("../../assets/images/maps/jaru-icon.png");
  background-repeat: no-repeat;
}
.map-wrapper {
  width: 950px;
  height: 999px;
  margin: 50px 0 0 -70px;
}
.btn2-1 {
  top: 190px;
  left: 130px;
  width: 105px;
  height: 110px;
}
.btn2-2 {
  top: 170px;
  left: 245px;
  width: 130px;
  height: 120px;
}
.btn2-3 {
  top: 95px;
  left: 320px;
  width: 120px;
  height: 75px;
}
.btn2-5 {
  top: 335px;
  left: 235px;
  width: 110px;
  height: 100px;
}
.btn2-6 {
  top: 445px;
  left: 320px;
  width: 115px;
  height: 110px;
}
.btn2-7 {
  top: 500px;
  left: 660px;
  width: 120px;
  height: 110px;
}
.btn2-8 {
  top: 615px;
  left: 650px;
  width: 125px;
  height: 160px;
}
.btn2-9 {
  top: 582px;
  left: 542px;
  width: 105px;
  height: 170px;
}
</style>
