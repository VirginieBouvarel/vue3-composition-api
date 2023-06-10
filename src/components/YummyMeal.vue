<template>
  <p>
    <strong>{{ name }}</strong>
    {{ pricePretty }}
  </p>
  <button @click="addToCart">Add to Cart</button>
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