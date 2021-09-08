<template>
  <div id="app">
    <HelloWorld :user-object="user" :title="title" @onChangeCounter="onChangeCounterInComponent" />
  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue';

export default {
  components: {
    HelloWorld,
  },
  data: () => ({
    title: 'Some title',
    user: {
      name: 'Vasya',
      age: 30,
    },
  }),
  methods: {
    onChangeCounterInComponent(value) {
      console.log('In App.vue, counter:', value);
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
