<template>
  <span>{{ pricePretty }}</span>
</template>
<script setup>
import { computed, inject, ref } from "vue";

const props = defineProps({
  price: Number,
});

const currencySymbol = inject("currencySymbol", ref("$"));
const pricePretty = computed(
  () => `${currencySymbol.value}${props.price.toFixed(2)}`
);

</script>