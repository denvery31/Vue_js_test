<template>
  <p>Hello</p>
  <div class="p_block">
    <div v-for="player in palyers" :key="player.name" class="player">
      {{ player.name }}
    </div>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      palyers: [
        {
          name: "kolya",
          age: 25,
        },
        {
          name: "petya",
          age: 20,
        },
        {
          name: "vasya",
          age: 30,
        },
      ],
    };
  },

  methods: {},
};
</script>

<style>
.p_block {
  background-color: red;
  padding: 10%;
  margin: 7%;
  border-radius: 35px;
}
</style>
