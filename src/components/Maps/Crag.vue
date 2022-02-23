<template>
  <div class="map-wrapper relative">
    <div class="bg-map absolute inset-0 z-0"></div>
    <div class="bg-pets absolute inset-0 z-10"></div>
    <div class="bg-icon absolute inset-0 z-20"></div>
    <div class="btns-wrap">
      <div v-for="index in [1,2,3,4,5,6,7]" :key="index" :class="'btn1-'+index" @click="showInfo(index)"></div>
    </div>
    <info-pet v-if="currentPet != null" :list-pets="dataPets" :currentPet="currentPet" @handle-close="handleClose" />
  </div>
</template>
<style scoped>
.bg-map {
  width: 100%;
  height: 100%;
  background-image: url("../../assets/images/maps/crag.png");
  background-size: cover;
  background-repeat: no-repeat;
}
.bg-pets {
  top: 50px;
  left: 92px;
  width: 672px;
  height: 537px;
  background-image: url("../../assets/images/maps/crag-pets.png");
  background-repeat: no-repeat;
}
.bg-icon {
  top: 84px;
  left: 200px;
  width: 495px;
  height: 470px;
  background-image: url("../../assets/images/maps/crag-icon.png");
  background-repeat: no-repeat;
}
.map-wrapper {
  width: 967px;
  height: 837px;
  margin: 50px 0 0 -50px;
}
.btn1-1 {
  top: 485px;
  left: 364px;
  width: 132px;
  height: 100px;
}
.btn1-2 {
  top: 287px;
  left: 482px;
  width: 110px;
  height: 80px;
}
.btn1-3 {
  top: 320px;
  left: 590px;
  width: 150px;
  height: 160px;
}
.btn1-4 {
  top: 60px;
  left: 300px;
  width: 125px;
  height: 90px;
}
.btn1-5 {
  top: 455px;
  left: 190px;
  width: 135px;
  height: 100px;
}
.btn1-6 {
  top: 70px;
  left: 440px;
  width: 130px;
  height: 150px;
}
.btn1-7 {
  top: 290px;
  left: 95px;
  width: 170px;
  height: 140px;
}
</style>
<script>
import InfoPet from './InfoPets/Pets.vue'
import TigerhogImge from '../../assets/images/pets/Tigerhog.png'
import CuekabitImge from '../../assets/images/pets/Cuekabit.png'
import PinoImge from '../../assets/images/pets/Pino.png'
import PinkpigImge from '../../assets/images/pets/Pinkpig.png'
export default {
    components: { InfoPet },
    methods: {
        showInfo(index){
            this.currentPet = index - 1

        },
        handleClose(){
            this.currentPet = null
             document.querySelector("body").classList.remove("overflow-hidden");
        }
    },
    data() {
        return {
            currentPet: null,
            dataPets: [{
                title: "Pinkpig Family",
                type: "Defense",
                desc: "Domesticated by the promise of food.",
                image: PinkpigImge,
                skill: "Trotter Strike",
                tags: ["#UnexpectedlyFast", "#Pig", "#GuardianPet", "#Hungry", "#FeedMeMore", "#ViolentMutants", "#Shield"],
                urlEmbed: "https://www.youtube.com/embed/EQaHxhnjavc"
            },{
                title: "Cuekabit Family",
                type: "Attack",
                desc: "A skittish friend that's sensitive to sound.",
                image: CuekabitImge,
                skill: "Injection Time",
                tags: ["#BigEars","#EarFlight", "#Visible", "#Sound", "#Surprised", "#Heal", "#Poison"],
                urlEmbed: "https://www.youtube.com/embed/QMJN6u6YnW4"
            },{
                title: "Pino Family",
                type: "Attack",
                desc: "A greedy pet who loves to eat.",
                image: PinoImge,
                skill: "Ever Onwards!",
                tags: ["#Swamp", "#RiverLife", "#Sunshine", "#NoTouchySails", "#YourFoodsMine", "#SomethingSmellsGood"],
                urlEmbed: "https://www.youtube.com/embed/Pc5rSTuH31g"
            },{
                title: "Beachtoise Family",
                type: "Defense",
                desc: "A thick and sturdy introvert.",
                image: PinkpigImge,
                skill: "I'm Your Shield",
                tags: ["#LiveLong", "#Wealth", "#MyShellIsMyHome", "#AgoaWeakling", "#CanFly"],
                urlEmbed: "https://www.youtube.com/embed/EQaHxhnjavc"
            },{
                title: "Tigerhog Family",
                type: "Defense",
                desc: "A stubborn and proud wild child.",
                image: TigerhogImge,
                skill: "Politeness",
                tags: ["#SpiritFriend", "#LoveShamans", "#Mogaros", "#SoWhat", "#Fancy", "#LegDay", "#EnergyRecovery"],
                urlEmbed: "https://www.youtube.com/embed/EQaHxhnjavc"
            }]
        }
    },
}
</script>