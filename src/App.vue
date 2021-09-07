<template>
  <div id="app">
    <h1>{{firstName}}</h1>
    <h2>{{num + 2}}</h2>
    <h3>{{ num > 1 ? 'Number > 1' : 'Number lower 1' }}</h3>
    <a :href="linkUrl">Link</a>
    <a :[attrKey]="linkUrl">Link</a>
    <template v-if="msgIsVisible === 1">
      <div class="message">Some Message!</div>
    </template>
    <template v-else-if="msgIsVisible === 2">
      <div class="message">V-If-Else Some Message!</div>
    </template>
    <template v-else>
      <div class="message">Else Message!</div>
    </template>

    <div v-show="isVisibleBlock">
      V Show Example
    </div>

    <div class="name-input" v-if="inputNameVisible">
      <label>Name</label>
      <input type="text" placeholder="input name" key="name-input">
    </div>
    <div class="nickname-input" v-else>
      <label>Nickname</label>
      <input type="text" placeholder="input nickname" key="nickname-input">
    </div>
    <button @click="inputNameVisible = !inputNameVisible">Change form</button>
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
    msgIsVisible: 1,
    isVisibleBlock: true,
    inputNameVisible: true,
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
