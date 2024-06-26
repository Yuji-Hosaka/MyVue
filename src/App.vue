<script setup>
const title = 'Vue.JS Learning'
let price = 9.99
function increment() {
  price += 1
  console.log(price)
}
</script>

<template>
  <h1>Title: {{ title }}</h1>
  <h2>Price: ${{ price - 1 }}</h2>
  <button @click="increment">OK</button>
</template>

<style></style>
