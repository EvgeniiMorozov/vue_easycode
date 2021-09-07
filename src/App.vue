<template>
  <div id="app">
    <button @click.right="onClick('some value', $event)">Click event</button>
    <a href @click.prevent="onLinkClick">Link</a>
    <h1>{{ text }}</h1>
    <input type="text" @keyup.enter="onKeyUp" />
  </div>
</template>

<script>
export default {
  data: () => ({
    text: '',
  }),
  methods: {
    onClick(value, e) {
      console.log(value, e);
    },
    onLinkClick() {
      console.log('link click');
    },
    onKeyUp(e) {
      console.log(e);
      this.text = e.target.value;
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
