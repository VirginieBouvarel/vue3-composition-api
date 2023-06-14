<template>
  <div class="flex">
    <p>
      <strong>{{ name }}</strong>
      <YummyMealPrice :price="price" />
    </p>
    <button @click="addToCart">Add to Cart</button>
  </div>
  
</template>

<script>
import YummyMealPrice from "./YummyMealPrice.vue";

export default {
  components: { YummyMealPrice },
  props: {
    name: String,
    price: Number,
  },
  setup(props, { emit }) {
    const addToCart = () => emit("addToCart", props.name);

    return { addToCart };
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