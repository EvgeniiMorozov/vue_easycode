<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <button @click="onClick">Send Event</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    title: {
      type: String,
      // required: true,
      default: 'Default Title',
    },
    userObject: {
      type: Object,
      validator(value) {
        console.log(value);
        return value.age;
      },
    },
  },
  data: () => ({
    counter: 0,
  }),
  methods: {
    onClick() {
      // console.log('click');
      this.counter += 1;
      this.$emit('onChangeCounter', this.counter);
    },
  },
};
</script>

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
