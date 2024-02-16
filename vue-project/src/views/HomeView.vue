<script setup>
import { createApp } from "vue";
import { createPinia } from "pinia";
import { ref, computed } from "vue";
// const Sidearm = [
//   {
//     Name: "Ghost",
//     Price: "500",
//   },
//   {
//     Name: "Classic",
//     Price: "0",
//   },
//   {
//     Name: "Frenzy",
//     Price: "450",
//   },
//   {
//     Name: "Shorty",
//     Price: "300",
//   },
//   {
//     Name: "Sherrif",
//     Price: "800",
//   },
// ];
// const Main = [
//   {
//     Name: "Vandal",
//     Price: "2900",
//   },
//   {
//     Name: "Phantom",
//     Price: "2900",
//   },
//   {
//     Name: "Bulldog",
//     Price: "2050",
//   },
//   {
//     Name: "Guardian",
//     Price: "2250",
//   },
//   {
//     Name: "Spectre",
//     Price: "1600",
//   },
//   {
//     Name: "Spectre",
//     Price: "1600",
//   },
//   {
//     Name: "Bucky",
//     Price: "850",
//   },
//   {
//     Name: "Judge",
//     Price: "1850",
//   },
//   {
//     Name: "Stinger",
//     Price: "1100",
//   },
//   {
//     Name: "Marshal",
//     Price: "950",
//   },
//   {
//     Name: "Outlaw",
//     Price: "2400",
//   },
//   {
//     Name: "Operator",
//     Price: "4700",
//   },
//   {
//     Name: "Ares",
//     Price: "1600",
//   },
//   {
//     Name: "Odin",
//     Price: "3200",
//   },
// ];

// Main.forEach(Guns);
// Sidearm.forEach(Pistol);

// function addPrice() {
//   `<p>${Guns.price} + ${Pistol.price}</p>`;
// }

// Define your Vue component
const num1 = ref(0);
const num2 = ref(0);

const sum = computed(() => {
  return parseInt(num1.value) + parseInt(num2.value);
});
</script>

<template>
  <main>
    <div id="app">
      <h1>adding thing</h1>
      <input type="number" v-model="num1" /> +
      <input type="number" v-model="num2" /> =
      <span>{{ sum }}</span>
    </div>
  </main>
</template>
