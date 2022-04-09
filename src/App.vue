<template>
  <!--<my-button :title="'Exit'" /> 
  <my-button title="Quite" /> -->
  <about-page @changePage="pageChanger" v-if="currentPage == 'about'" />
  <room-creation v-if="currentPage == 'creation'" />
  <room-joining v-if="currentPage == 'joining'" :players="palyers" />
  <game-process v-if="currentPage == 'process'" />
</template>

<script>
import roomJoining from "@/components/mainComponents/roomJoining.vue";
import roomCreation from "@/components/mainComponents/roomCreation.vue";
import gameProcess from "@/components/mainComponents/gameProcess.vue";
import aboutPage from "@/components/mainComponents/aboutPage.vue";

export default {
  name: "App",
  components: {
    roomJoining,
    roomCreation,
    gameProcess,
    aboutPage,
  },
  methods: {
    pageChanger(where) {
      this.currentPage = where;
    },
  },
  data() {
    return {
      currentPage: "about",

      your_id: 1,
      palyers: [
        {
          name: "Kolya",
          ready: false,
        },
        {
          name: "Petya",
          ready: false,
        },
        {
          name: "Vasya",
          ready: false,
        },
        {
          name: "Dmitriy",
          ready: false,
        },
      ],
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans&display=swap");

body {
  background-color: rgb(245, 242, 239);
  opacity: 70%;

  font-family: "Noto Sans", sans-serif;
  font-size: 2.4rem;
  color: rgb(16, 40, 14);
}
</style>
