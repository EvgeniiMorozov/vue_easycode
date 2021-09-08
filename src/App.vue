<template>
  <div id="app">
    <h1>Hello {{ fullName }}</h1>
    <input type="text" @keyup.enter="setName" />
  </div>
</template>

<script>
export default {
  data: () => ({
    firstName: '',
    lastName: '',
  }),
  methods: {
    setName(e) {
      // this.firstName = e.target.value;
      this.fullName = e.target.value;
    },
    onLastNameUpdate(value) {
      console.log('watch', value);
    },
  },
  computed: {
    fullName: {
      get() {
        return `${this.firstName || 'Default'} ${this.lastName || 'User'}`;
      },
      set(value) {
        console.log(value);
        const [firstName, lastName] = value.split(' ');
        console.log(firstName, lastName);
        this.firstName = firstName;
        this.lastName = lastName;
      },
    },
  },
  watch: {
    lastName: 'onLastNameUpdate',
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
