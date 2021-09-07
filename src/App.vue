<template>
  <div id="app">
    <h1>{{firstName}}</h1>
    <h2>{{num + 2}}</h2>
    <h3>{{ num > 1 ? 'Number > 1' : 'Number lower 1' }}</h3>
    <a :href="linkUrl">Link</a>
    <a :[attrKey]="linkUrl">Link</a>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {

  },
  data: () => ({
    firstName: 'Evgeniy',
    num: 2,
    linkUrl: 'https://google.ru',
    attrKey: 'href',
  }),
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
