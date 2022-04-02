<template>
  <p class="headder">Wating for other playes...</p>
  <div class="p_block">
    <p class="p_top">Palyers:</p>
    <div class="p_playres">
      <div v-for="player in palyers" :key="player.name" class="player">
        <p>{{ player.name }}</p>
        <p>Ready: {{ player.ready }}</p>
      </div>
    </div>
    <div class="btn">
      <button
        @click="
          this.palyers[this.your_id].ready
            ? make_all_not_ready()
            : make_all_ready()
        "
        class="btn_ready"
      >
        {{ this.palyers[this.your_id].ready ? "Canel" : "Ready" }}
      </button>
      <button v-if="!each_player_ready()" class="btn_exit">Exit</button>
      <button v-if="each_player_ready()" class="btn_start">Start</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      your_id: 1,
      palyers: [
        {
          name: "Kolya",
          age: 25,
          ready: false,
        },
        {
          name: "Petya",
          age: 20,
          ready: false,
        },
        {
          name: "Vasya",
          age: 30,
          ready: false,
        },
        {
          name: "Dmitriy",
          age: 12,
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
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans&display=swap");
body {
  font-family: "Noto Sans", sans-serif;
  font-size: 2.4rem;
  background-color: rgb(245, 242, 239);
}

.headder {
  text-align: center;
}

.p_playres {
  max-width: 100%;
}

.p_playres p {
  max-width: 90%;
  margin: auto;
}

.p_playres > .player {
  border-bottom: 0.1rem solid rgb(52, 129, 35);
  display: flex;
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

.btn button {
  border: none;
  padding: 2%;
  border-radius: 12px;
  width: 15%;
  margin: 0 3%;
  background-color: rgb(227, 213, 194);
}

.btn button:hover {
  opacity: 80%;
  cursor: pointer;
}
</style>
