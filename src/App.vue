<template>
  <h1>{{  name }}</h1>
  <input type="text" v-model="name">
  <button @click="placeOrder">Place Order</button>
  <button @click="removeWatcher">Hide cart Alerts</button>
  <YummyMeal v-for="meal in meals" :name="meal.name" :price="meal.price" @addToCart="addItemToCart"/>
  
</template>

<script>
import YummyMeal from './components/YummyMeal.vue';
import { ref, reactive, watchEffect } from 'vue';

export default {
  components: { YummyMeal},
  setup() {
    const name = ref('The Snazzy Burger');
    const cart = reactive([]);
    const meal = reactive({ name: "Hambuger", price: 5 });
    const meals = reactive([
      { name: "Hambuger", price: 5 },
      { name: "Cheeseburger", price: 6 },
      { name: "Impossible Burger", price: 7 },
      { name: "Fries", price: 2 },
    ]);

    const placeOrder = () => alert("You're order has been placed!");
    const addItemToCart = (item) => cart.push(item);

    const removeWatcher = watchEffect(() => alert(cart.join("\n")));

    return { name, meal, meals, placeOrder, addItemToCart, removeWatcher };
  },
}
</script>
