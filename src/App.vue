<template>
  <div id="app">
    <ul>
      <!--      <li v-for="(color, index) in colors" :key="index">
      {{ index + 1 }} {{ color }}
      </li>-->
      <!--      <li v-for="user in users" :key="user.id">{{ user.name }} : {{ user.age }}</li>-->
      <li v-for="(value, name, index) in product" :key="index">
        {{ index + 1 }} {{ name }}: {{ value }}
      </li>
    </ul>
    <div>
      <!--      <input type="text" @keyup.enter="addNewColor" />-->
      <input type="text" @keyup.enter="deleteProp" />
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    colors: ['orange', 'yellow', 'black'],
    users: [
      { name: 'Denis', age: 30, id: '1' },
      { name: 'Ivan', age: 25, id: '2' },
    ],
    product: {
      brand: 'Apple',
      model: 'IPhone 12',
      price: '$1000',
    },
  }),
  methods: {
    addNewColor(e) {
      // this.colors.push(e.target.value);
      console.log(e.target.value);
      // this.colors[this.colors.length] = e.target.value;
      this.$set(this.colors, this.colors.length, e.target.value);
    },
    deleteProp(e) {
      console.log(e.target.value);
      // delete this.product[e.target.value];
      this.$delete(this.product, e.target.value);
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
