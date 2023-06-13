<template>
  <div class="flex">
    <p>
      <strong>{{ name }}</strong>
      {{ pricePretty }}
    </p>
    <button @click="addToCart">Add to Cart</button>
  </div>
  
</template>

<script>
import { computed } from 'vue';

export default {
  props: {
    name: String,
    price: Number,
  },
  setup(props, { emit }) {
    const addToCart = () => emit("addToCart", props.name);
    const pricePretty = computed(() => `$${props.price.toFixed(2)}`);

    return { addToCart, pricePretty };
  }
}
</script>

<style scoped>
.flex {
  display: flex;
  justify-content: space-between;
  margin: 4px 0;
}
</style>