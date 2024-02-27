<template>
  <div :class="ShoppingCartClass">
    <h2>ShoppingCart</h2>
    <li v-for="(cartItem, index) in cart" :key="index">
      {{ cartItem.Name }}-${{ cartItem.Price }}
    </li>
    <p>Total Cost:${{ addtotalCost }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const ShoppingCartClass = ref("Shoppingcart");

const cart = ref([]);

const addtotalCost = computed(() => {
  return cart.value.reduce((total, item) => total + parseInt(item.Price), 0);
});
</script>

<style scoped>
.Shoppingcart {
  width: 30%;
  margin-right: 50%;
}
</style>
