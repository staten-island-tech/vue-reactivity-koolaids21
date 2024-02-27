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
  <div :class="containerClass">
    <div :class="ListClass">
      <h1 :class="titleClass">Valorant Shop</h1>
      <div v-for="(item, index) in Main" :key="index" :class="cardClass">
        <p>{{ item.Name }}- ${{ item.Price }}</p>
        <button @click="additem(item)">Add to Cart</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-right: 50%;
  padding: 10px;
}

.card {
  margin: 2.5rem 0;
  height: 100px;
  width: 2vw;
  background-color: rgba(65, 65, 150, 0.6);
  border-radius: 12px;
}
.Shoppingcart {
  width: 30%;
  margin-right: 50%;
}

.container {
  display: flex;
  justify-content: space-around;
}
.title {
  font-size: 3rem;
  text-align: center;
}
</style>
