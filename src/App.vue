<template>
  <!--<my-button :title="'Exit'" /> 
  <my-button title="Quite" /> -->

  <p class="headder">Wating for other playes...</p>
  <div class="p_block">
    <p class="p_top">Palyers:</p>
    <div class="p_playres">
      <div v-for="player in palyers" :key="player.name" class="player">
        <span>{{ player.name }}</span>
        <span>Ready: {{ player.ready }}</span>
      </div>
    </div>

    <button
      @click="
        this.palyers[this.your_id].ready
          ? make_all_not_ready()
          : make_all_ready()
      "
    >
      {{ this.palyers[this.your_id].ready ? "Canel" : "Ready" }}
    </button>
    <my-button v-if="!each_player_ready()" :title="'Exit'" />
    <my-button v-if="each_player_ready()" :title="'Start'" />
  </div>
</template>

<script>
import myButton from "@/components/globalComponents/myButton.vue";
export default {
  name: "App",
  components: {
    myButton,
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

  methods: {
    each_player_ready() {
      for (let player of this.palyers) {
        if (!player.ready) {
          return false;
        }
      }
      return true;
    },
    make_all_ready() {
      this.palyers.forEach((player) => {
        player.ready = true;
      });
    },
    make_all_not_ready() {
      this.palyers.forEach((player) => {
        player.ready = false;
      });
    },
    someMethod() {
      alert("Imm gaaay");
      console.log("maam");
    },
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

.headder {
  text-align: center;
}

.p_playres {
  max-width: 100%;
}

.p_playres span {
  margin-left: 7%;
}

.p_playres > .player {
  display: flex;

  border-bottom: 0.1rem solid rgb(52, 129, 35);
}

.p_top {
  border-bottom: 0.2rem solid rgb(53, 70, 15);

  margin: 0;
  margin-bottom: 2%;
}

.p_block {
  padding: 3%;

  max-width: 50%;
  margin: auto;

  border: 0.3rem solid rgb(168, 212, 73);
  border-radius: 35px;

  background-color: rgba(255, 255, 255, 0.496);
}
</style>
