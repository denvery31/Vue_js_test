<template>
  <p class="headder">Wating for other playes...</p>

  <div class="p_block">
    <p>Palyers:</p>
    <div class="p_playres">
      <div v-for="player in players" :key="player.name" class="player">
        <span>{{ player.name }}</span>
        <!--<span>{{ player.ready ? "ready" : "not ready" }}</span>-->
      </div>
    </div>
    <div class="btns">
      <div><my-button :title="'Start'" /></div>
      <div><my-button :title="'Exit'" /></div>
      <div><my-button :title="'Ready'" /></div>
    </div>
    <!-- <button
      @click="
        this.palyers[this.your_id].ready
          ? make_all_not_ready()
          : make_all_ready()
      "
    >
      {{ this.palyers[this.your_id].ready ? "Canel" : "Ready" }}
    </button> -->
    <!--<my-button v-if="!each_player_ready()" :title="'Exit'" />
    <my-button v-if="each_player_ready()" :title="'Start'" />-->
  </div>
</template>

<script>
import myButton from "@/components/globalComponents/myButton.vue";
export default {
  name: "App",
  components: {
    myButton,
  },
  props: {
    players: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      your_id: 1,
    };
  },

  methods: {},
};
</script>

<style scoped>
.headder {
  text-align: center;
}

.p_playres {
  max-width: 100%;
  border-bottom: 0.15rem solid rgb(53, 70, 15);
  border-top: 0.15rem solid rgb(53, 70, 15);
}

.p_playres span {
  margin-left: 7%;
}

.p_playres > .player {
  display: flex;
  border-bottom: 0.1rem solid rgb(52, 129, 35);
}

.p_playres > .player:last-child {
  border-bottom: 0;
}

.p_block p {
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

.btns > div {
  max-width: 100%;
  display: inline;
  margin: 5.1%;
}
</style>
