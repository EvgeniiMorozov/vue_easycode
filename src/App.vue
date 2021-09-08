<template>
  <div id="app">
    <h1 class="title" :class="[classObj, activeClass]" :style="{ 'font-size': fontSize + 'px' }">
      Hello World
    </h1>
  </div>
</template>

<script>
export default {
  data: () => ({
    activeClass: 'my-active-class',
    isActive: false,
    fontSize: 30,
  }),
  computed: {
    classObj() {
      return {
        'active-class': this.isActive,
        error: !this.isActive,
      };
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
