<template>
  <p>Wating for other playes...</p>
  <div class="p_block">
    <p class="p_top">Palyers:</p>
    <div class="p_playres">
      <div v-for="player in palyers" :key="player.name" class="player">
        <p>{{ player.name }}</p>
      </div>
    </div>
    <button>Start</button>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      palyers: [
        {
          name: "Kolya",
          age: 25,
        },
        {
          name: "Petya",
          age: 20,
        },
        {
          name: "Vasya",
          age: 30,
        },
        {
          name: "Dmitriy",
          age: 12,
        },
      ],
    };
  },

  methods: {},
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans&display=swap");
body {
  font-family: "Noto Sans", sans-serif;
  font-size: 2.4rem;
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
}
</style>
