<template>
  <p><strong>{{  name }}</strong></p>
  <button @click="addToCart">Add to Cart</button>
</template>

<script>
export default {
  props: {
    name: String,
    price: Number,
  },
  setup(props, { attrs, slots, emit }) {
    console.log(props.name);
    console.log(props.price);

    const addToCart = () => emit("addToCart", props.name);

    return { addToCart };
  }
}
</script>