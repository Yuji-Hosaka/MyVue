<script setup>
import { ref } from 'vue'

const title = ref('Vue.JS Learning')
let price = ref(9.99)
function increment() {
  price.value += 1
}

const info = ref({
  students: 1000,
  rating: 4
})
console.log(info.value.students)
</script>

<template>
  <!-- No need .value here, otherwise, it will be NaN -->
  <h1>Title: {{ title }}</h1>
  <h2>Price: ${{ price - 1 }}</h2>
  <button @click="increment">OK</button>
  <h2>Student: {{ info.students }}</h2>
</template>

<style></style>
