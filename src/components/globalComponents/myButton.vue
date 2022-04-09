<template>
  <div>
    <button class="btn">{{ title }}</button>
  </div>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
  },
  methods: {},
};
</script>

<style scoped>
button {
  background-color: rgb(213, 227, 194);

  border: none;
  border-radius: 5em/5em;

  padding: 1% 3%;
  transition: 0.3s linear;
}
button:hover {
  box-shadow: 0 0 0 2px rgb(213, 227, 194) inset,
    0 0 0 4px rgb(245, 242, 239) inset;
  cursor: pointer;
}
</style>
