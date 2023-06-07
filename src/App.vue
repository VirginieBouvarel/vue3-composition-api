<template>
  <h1>{{  name }}</h1>
  <input type="text" v-model="name">
  <button @click="placeOrder">Place Order</button>
  <YummyMeal name="Hamburger" :price="5" @addToCart="addItemToCart"/>
</template>

<script>
import YummyMeal from './components/YummyMeal.vue';
import { ref } from 'vue';

export default {
  components: { YummyMeal},
  setup() {
    const name = ref('The Snazzy Burger');
    name.value = 'Hello from the setup function';
    console.log("%c in setup --name.value :","color: yellow", name.value);

    const placeOrder = () => alert("You're order has been placed!");
    const addItemToCart = (item) => alert(`One ${item} added to the cart!`);

    return { name, placeOrder, addItemToCart };
  },
  created() {
    this.name = 'Hello from the created hook !';
    console.log("%c in created --name :","color: yellow", this.name);

  }
}
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
