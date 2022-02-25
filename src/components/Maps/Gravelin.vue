<template>
  <div class="map-wrapper relative">
    <div class="bg-map absolute inset-0 z-0"></div>
    <div class="bg-pets absolute inset-0 z-10"></div>
    <div class="bg-icon absolute inset-0 z-20"></div>
    <div class="btns-wrap">
      <div
        v-for="index in [1, 2, 3, 4, 5]"
        :key="index"
        :class="'btn3-' + index"
        @click="showInfo(index)"
      ></div>
    </div>
    <info-pet
      v-if="currentPet != null"
      :list-pets="dataPets"
      :currentPet="currentPet"
      @handle-close="handleClose"
      @change-slide="changeSlide"
    />
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
  max-width: 100%;
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
<script>
import InfoPet from "./InfoPets/Pets.vue";
import ManmoImge from "../../assets/images/pets/Manmo.png";
import YangidonImge from "../../assets/images/pets/Yangidon.png";
import PlacobiImge from "../../assets/images/pets/Placobi.png";
import KatargasImge from "../../assets/images/pets/Katargas.png";
import ClobgorImge from "../../assets/images/pets/Clobgor.png";
export default {
  components: { InfoPet },
  methods: {
    showInfo(index) {
      this.currentPet = index - 1;
    },
    handleClose() {
      this.currentPet = null;
      document.querySelector("body").classList.remove("overflow-hidden");
    },
    changeSlide(index) {
      this.showInfo(index + 1);
    },
  },
  data() {
    return {
      currentPet: null,
      dataPets: [
        {
          title: "Manmo Family",
          type: "Defense",
          desc: "An active trickster who isn't bothered by the cold.",
          image: ManmoImge,
          skill: "Ancient Power",
          desKill: "Heals 1 ally based on their Max HP, decreases DMG received.",
          tags: [
            "#LongFur",
            "#Bus",
            "#Friendly",
            "#SkinnierThanPrachius",
            "#BeCareful",
            "#BodySlam",
          ],
          urlEmbed: "https://www.youtube.com/embed/DedswdcXdCs",
        },
        {
          title: "Yangidon Family",
          type: "Attack",
          desc: "A competitive-born fighter.",
          image: YangidonImge,
          skill: "Become a Star!",
          desKill: "Deals heavy DMG to 1 target.",
          tags: [
            "#FiveBrothers",
            "#PeckingOrder",
            "#Fights",
            "#Brave",
            "#FullBodyWeapon",
            "#FightingSpirit",
            "#Force",
            "#EndlessAssault",
            "#Powerful",
          ],
          urlEmbed: "https://www.youtube.com/embed/AbaIqxUwvP8",
        },
        {
          title: "Placobi Family",
          type: "Attack",
          desc: "A sensitive and cautious cave dweller.",
          image: PlacobiImge,
          skill: "Round the World",
          desKill: "Standby 1 turn and deal heavy DMG that ignores defense.",
          tags: [
            "#Dad", "#Mom", "#Brother", "#Sister", "#All", "#Family", "#SonicWaves", "#Communication", "#Eyesight", "#Bad", "#PlacobiFlights", "#TheSunBurns", "#NightOwl"
          ],
          urlEmbed: "https://www.youtube.com/embed/wkzevbzSl1A",
        },
        {
          title: "Katargas Family",
          type: "Defense",
          desc: "A passive yet self-sacrificing slob.",
          image: KatargasImge,
          skill: "Defensive Curl",
          desKill: "Increases defense, Reflect Chance and Reflect Effect. Heal reflected DMG.",
          tags: [
            "#StrongestShield", "#Kaki", "#BullyYou", "#RoundnRound", "#ILoveMyTree",
          ],
          urlEmbed: "https://www.youtube.com/embed/EaVTNt6kktE",
        },{
          title: "Clobgor Family",
          type: "Attack",
          desc: "An anger-prone meanie.",
          image: ClobgorImge,
          skill: "I'm Angry!",
          desKill: "Deals DMG to 1 target and an enemy behind it.",
          tags: [
            "#BigBoned", "#AngerIssues", "#Fist", "#Spin", "#NeabyObjects","#AtRisk"
          ],
          urlEmbed: "https://www.youtube.com/embed/g7V36110CMQ",
        },
      ],
    };
  },
};
</script>
