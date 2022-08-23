<template>
  <div class="menu">
    <a v-for="a in menus" :key="a"> {{ a }}</a>
  </div>
  <div v-for="(product, i) in products" :key="product">
    <h4>{{ product }}</h4>
    <p>{{ price[i] }}만원</p>
    <button v-on:click="increase(i)">신고</button> <span>{{ count[i]}}</span>
  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      price: [60, 70, 30],
      menus: ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '개똥이원룸', '성현이원룸'],
      count: [0, 0, 0]
    }
  },
  methods: {
    increase(i) {
      this.count[i] += 1;
    }
  },
  components: {

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;

}
</style>
