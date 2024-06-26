<script setup>
import { ref, reactive } from 'vue'

const title = ref('Vue.JS Learning')
let price = ref(9.99)
function increment() {
  price.value += 1
  instructor.age -= 1
  info.value.students += 1
  instructor.nationality = 'Japanese'
  instructor.sns.twitter = '@__yoshipi__@'
}

const info = ref({
  students: 1000,
  rating: 4
})

const instructor = reactive({
  name: 'Yoshipi',
  age: 25,
  sns: {
    twitter: '@__yoshipi__',
    youtube: '@yoshipi'
  }
})

instructor.nationality = '???'
console.log(instructor.name)
console.log(info.value.students)
</script>

<template>
  <!-- No need .value here, otherwise, it will be NaN -->
  <button @click="increment">Click me!!</button>
  <h1>Title: {{ title }}</h1>
  <h2>Price: ${{ price - 1 }}</h2>
  <h2>Student: {{ info.students }}</h2>
  <h2>Instructor age: {{ instructor.age }}</h2>
  <h2>Instructor nationality: {{ instructor.nationality }}</h2>
  <h2>Instructor sns twitter: {{ instructor.sns.twitter }}</h2>
</template>

<style></style>
