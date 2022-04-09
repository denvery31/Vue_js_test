<template>
  <p class="headder">About Page</p>

  <div class="p_block">
    <p>Go to:</p>
    <div class="p_playres">
      <select v-model="page">
        <option value="about">Home</option>
        <option value="creation">Creation</option>
        <option value="joining">Join</option>
        <option value="process">Game</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},

  data() {
    return {
      page: "about",
    };
  },
  watch: {
    page(value) {
      this.$emit("changePage", value);
    },
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

  padding: 5%;
}

.p_block {
  padding: 3%;

  max-width: 50%;
  margin: auto;

  border: 0.3rem solid rgb(168, 212, 73);
  border-radius: 1em/1em;

  background-color: rgba(255, 255, 255, 0.496);
}

.p_block p:first-child {
  margin: 0;
}

.p_playres > div {
  max-width: 100%;
  display: inline;
  margin: 5.1%;
}
.p_playres > select {
  background-color: rgb(213, 227, 194);

  border: none;
  border-radius: 5em/5em;

  width: 30%;
  padding: 4%;

  transition: 0.3s linear;
}
</style>
