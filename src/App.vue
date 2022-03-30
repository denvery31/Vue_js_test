<template>
  <p>Hello</p>
  <div>
    <div v-for="player in palyers" :key="player">
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

<style></style>
