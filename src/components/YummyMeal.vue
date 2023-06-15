<template>
  <div class="flex">
    <p>
      <strong>{{ name }}</strong>
      <YummyMealPrice :price="price" />
    </p>
    <button @click="addToCart">Add to Cart</button>
  </div>
  
</template>

<script setup>
import YummyMealPrice from "./YummyMealPrice.vue";

const props = defineProps({
  name: String,
  price: Number,
});
const emit = defineEmits(["addToCart"]);

const addToCart = () => emit("addToCart", props.name);

</script>

<style scoped>
.flex {
  display: flex;
  justify-content: space-between;
  margin: 4px 0;
}
</style>