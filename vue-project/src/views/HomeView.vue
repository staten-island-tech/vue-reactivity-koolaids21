<script setup>
import { ref, computed } from "vue";
import { Main } from "./array.vue";

const cart = ref([]);

const additem = (item) => {
  cart.value.push(item);
};

const addtotalCost = computed(() => {
  return cart.value.reduce((total, item) => total + parseInt(item.Price), 0);
});

const containerClass = ref("container");
const ListClass = ref("list");
const titleClass = ref("title");
const cardClass = ref("card");
</script>

<template>
      <h1 :class="titleClass">Valorant Shop</h1>
  <div :class="containerClass">
    <div :class="ListClass">
      <div v-for="(item, index) in Main" :key="index" :class="cardClass">
        <p>{{ item.Name }}- ${{ item.Price }}</p>
        <button @click="additem(item)">Add to Cart</button>
      </div>
    </div>
    <div :class="ShoppingCartClass">
      <h2>ShoppingCart</h2>
      <li v-for="(cartItem, index) in cart" :key="index">
        {{ cartItem.Name }}-${{ cartItem.Price }}
      </li>
      <p>Total Cost:${{ addtotalCost }}</p>
    </div>
  </div>
</template>

<style scoped>
.list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 10px;
}

.card {
  height: 100px;
  width: 15vw;
  background-color: rgba(65, 65, 150, 0.6);
  border-radius: 12px;
  margin-top: 20px;
  text-align: center;
  margin-right: 100px;
}
.Shoppingcart {
  width: 30%;
}

.container {
  display: flex;
  justify-content: space-around;
  flex-direction: row;
}
.title {
  font-size: 3rem;
  text-align: center;
}
</style>
