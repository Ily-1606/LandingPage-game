<template>
  <div class="map-wrapper relative">
    <div class="bg-map absolute inset-0 z-0"></div>
    <div class="bg-pets absolute inset-0 z-10"></div>
    <div class="bg-icon absolute inset-0 z-20"></div>
    <div class="btns-wrap">
      <div
        v-for="index in [1, 2, 3, 4, 5, 6, 7, 8]"
        :key="index"
        :class="'btn2-' + index"
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
  max-width: 100%;
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
.btn2-4 {
  top: 335px;
  left: 235px;
  width: 110px;
  height: 100px;
}
.btn2-5 {
  top: 445px;
  left: 320px;
  width: 115px;
  height: 110px;
}
.btn2-6 {
  top: 500px;
  left: 660px;
  width: 120px;
  height: 110px;
}
.btn2-7 {
  top: 615px;
  left: 650px;
  width: 125px;
  height: 160px;
}
.btn2-8 {
  top: 582px;
  left: 542px;
  width: 105px;
  height: 170px;
}
</style>
<script>
import InfoPet from "./InfoPets/Pets.vue";
import PoboImge from "../../assets/images/pets/Pobo.png";
import PinkiImge from "../../assets/images/pets/Pinki.png";
import OtutuImge from "../../assets/images/pets/Otutu.png";
import WatakaImge from "../../assets/images/pets/Wataka.png";
import KucoskiImge from "../../assets/images/pets/Kucoski.png";
import PentasImge from "../../assets/images/pets/Pentas.png";
import KakiImge from "../../assets/images/pets/Kaki.png";
import PrachiusImge from "../../assets/images/pets/Prachius.png";
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
          title: "Wataka Family",
          type: "Heal",
          desc: "A curious and fearless forest shaman.",
          image: WatakaImge,
          skill: "Growing Vines",
          desKill: "All allies heal based on their Max HP.",
          tags: [
            "#SpiritGrass",
            "#FlowerCrown",
            "#OnHead",
            "#Spells",
            "#Heal",
            "#MyPrecious",
            "#OnHead",
            "#ShowOff",
          ],
          urlEmbed: "https://www.youtube.com/embed/vrY66diH84c",
        },
        {
          title: "Pinki Family",
          type: "Suppress",
          desc: "A curious and loveable bundle of joy.",
          image: PinkiImge,
          skill: "Critical Charm",
          desKill: "Has a chance to apply [Charm] to 3 enemies.",
          tags: [
            "#Wink",
            "#LookAtMe",
            "#Your",
            "#Face",
            "#Looks",
            "#Funny",
            "#LOL",
            "#JustKidding",
          ],
          urlEmbed: "https://www.youtube.com/embed/seTfdBTY5P8",
        },
        {
          title: "Otutu Family",
          type: "Suppress",
          desc: "A gentle and curious busybody who loves Hide and Seek.",
          image: OtutuImge,
          skill: "Forest Song",
          desKill: "Deals DMG that ignores defense to 3 targets and has a chance to remove Buff and heal.",
          tags: [
            "#Leaf",
            "#Stone",
            "#LikeHiding",
            "#FindMe",
            "#LotsaFriends",
            "#LikeHumans",
          ],
          urlEmbed: "https://www.youtube.com/embed/5_qX2q8BvHA",
        },
        {
          title: "Kucoski Family",
          type: "Attack",
          desc: "A smart and friendly trickster.",
          image: KucoskiImge,
          skill: "220 Volts!",
          desKill: "Deals DMG to 1 target and decreased Energy.",
          tags: [
            "#DroopyEyes",
            "#Pitiful",
            "#Calm",
            "#MonsterWhenAngry",
            "#Human",
            "#Friend",
          ],
          urlEmbed: "https://www.youtube.com/embed/zxMkJt9ukMI",
        },
        {
          title: "Pobo Family",
          type: "AOE",
          desc: "A easygoing outlaw from the swamp.",
          desKill: "Deals DMG to 1 target and decreased Energy.",
          image: PoboImge,
          skill: "Refreshing Walk",
          tags: [
            "#Past",
            "#Underwater",
            "#Current",
            "#Land",
            "#Evolve",
            "#HighHumidity",
            "#PoisonSkin",
            "#SprayPoisonWhenThreatened",
            "#GoldBoy",
            "#SilverBoy",
          ],
          urlEmbed: "https://www.youtube.com/embed/4e17Bagm7NY",
        },
        {
          title: "Pentas Family",
          type: "Suppress",
          desc: "The best dancer in Tectonika who likes to be fancy.",
          image: PentasImge,
          skill: "Hula Dance",
          desKill: "Increases Energy of multiple allies, heals ally HP.",
          tags: [
            "#ManeSensitive",
            "#GrassFashion",
            "#LookingForLove",
            "#Dance",
            "#DontWannaMove",
            "#LikeFruit",
            "#Gigaros",
            "#FlapsAnnoyMe",
            "#HornsOnMales",
          ],
          urlEmbed: "https://www.youtube.com/embed/J96V7TbPFvA",
        },
        {
          title: "Kaki Family",
          type: "AOE",
          desc: "An edgy yet cautious gasbag.",
          image: KakiImge,
          skill: "Mystical Match",
          desKill: "Deals DMG to target and all enemies in the same row, has a chance to apply [Confuse].",
          tags: [
            "#Beachtoise",
            "#Katargas",
            "#ILikeRoundThings",
            "#Indigestion",
            "#Farty",
            "#Flammable",
            "#FlockLife",
            "#Running",
          ],
          urlEmbed: "https://www.youtube.com/embed/h7PXPHrh5s4",
        },{
          title: "Prachius Family",
          type: "Defense",
          desc: "The most laid-back and largest forest guardian in Tectonika.",
          desKill: "Deals DMG to target and all enemies in the same row, has a chance to apply [Confuse].",
          image: PrachiusImge,
          skill: "Giga Stomp",
          tags: [
            "#5.0Vision", "#NeckSnap", "#NeckDisc", "#BeChill", "#Shield", "#WhenInDanger", "#SummonFriends", "#StepOnIt", "#Riddles"
          ],
          urlEmbed: "https://www.youtube.com/embed/XWvF7ENBx_4",
        },
      ],
    };
  },
};
</script>
