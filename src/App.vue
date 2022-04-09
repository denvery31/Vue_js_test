<template>
  <!--<my-button :title="'Exit'" /> 
  <my-button title="Quite" /> -->
  <room-joining :players="palyers" />
</template>

<script>
import roomJoining from "@/components/mainComponents/roomJoining.vue";

export default {
  name: "App",
  components: {
    roomJoining,
  },
  data() {
    return {
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
