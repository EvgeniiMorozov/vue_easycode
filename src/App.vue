<template>
  <div id="app">
    <button @click="onClick">Click event</button>
  </div>
</template>

<script>
export default {
  data: () => ({}),
  methods: {
    onClick(e) {
      console.log('click', e);
    },
  },
};
</script>

<style scoped></style>
