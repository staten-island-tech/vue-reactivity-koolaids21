<script setup>
import { createApp } from "vue";
import { createPinia } from "pinia";
import { ref, computed } from "vue";

const Main = [
  {
    Name: "Ghost",
    Price: "500",
  },
  {
    Name: "Classic",
    Price: "0",
  },
  {
    Name: "Frenzy",
    Price: "450",
  },
  {
    Name: "Shorty",
    Price: "300",
  },
  {
    Name: "Sherrif",
    Price: "800",
  },
  {
    Name: "Vandal",
    Price: "2900",
  },
  {
    Name: "Phantom",
    Price: "2900",
  },
  {
    Name: "Bulldog",
    Price: "2050",
  },
  {
    Name: "Guardian",
    Price: "2250",
  },
  {
    Name: "Spectre",
    Price: "1600",
  },
  {
    Name: "Spectre",
    Price: "1600",
  },
  {
    Name: "Bucky",
    Price: "850",
  },
  {
    Name: "Judge",
    Price: "1850",
  },
  {
    Name: "Stinger",
    Price: "1100",
  },
  {
    Name: "Marshal",
    Price: "950",
  },
  {
    Name: "Outlaw",
    Price: "2400",
  },
  {
    Name: "Operator",
    Price: "4700",
  },
  {
    Name: "Ares",
    Price: "1600",
  },
  {
    Name: "Odin",
    Price: "3200",
  },
  {
    Name: "Light Armor",
    Price: "400",
  },
  {
    Name: "Heavy Armor",
    Price: "1000",
  },
];

const cart = ref([]);

const additem = (item) => {
  cart.value.push(item);
};

const addtotalCost = computed(() => {
  return cart.value.reduce((total, item) => total + parseInt(item.Price), 0);
});
</script>

<template>
  <div class="container">
    <div class="list">
      <h1 class="title">Valorant Shop</h1>
      <div v-for="(item, index) in Main" :key="index" class="card">
        <p>{{ item.Name }}- ${{ item.Price }}</p>
        <button @click="additem(item)">Add to Cart</button>
      </div>
    </div>
    <div class="Shoppingcart">
      <h2>ShoppingCart</h2>
      <li v-for="(cartItem, index) in cart" :key="index">
        {{ cartItem.Name }}-${{ cartItem.Price }}
      </li>
      <p>Total Cost:${{ addtotalCost }}</p>
    </div>
  </div>
</template>

<style>
body {
  background-image: url("https://www.pixground.com/wp-content/uploads/2023/08/Valorant-Agents-4K-Wallpaper-jpg.webp");
}
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
body {
  width: 80%;
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
