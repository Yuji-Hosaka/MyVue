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
  instructor.email = 'info@example.com'
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
  },
  email: ref('yoshipi@mail.com')
})

const items = reactive([ref(1), ref(2), ref(3)])
items.reverse()
const courseInfo = {
  section: ref(10),
  language: 'Japanese'
}

const sections = courseInfo.section.value
console.log(sections)

// instructor.nationality = '???'
// console.log(instructor.name)
// console.log(info.value.students)
// console.log(instructor.email)
// console.log(items[0])
// console.log(items[0].value)
// console.log(courseInfo.section.value)
// console.log(courseInfo.language)
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
  <h2>Instructor email: {{ instructor.email }}</h2>
  <!-- <h2>Instructor sections: {{ courseInfo.section }}</h2>  -->
  <h2>Instructor sections: {{ sections + 102 }}</h2>
  <h2>Instructor language: {{ courseInfo.language }}</h2>

  <h1 class="ketsu-ron">結論</h1>
  <h2>
    オブジェクトをリアクティブにしたい場合レフ関数とリアクティブ関数、どっち使ったらいいのか？
  </h2>
  <h2 class="kotae">
    公式のドキュメントでは基本的にはレフ関数を使いましょうということがお勧めされています。
    <br />
    なので、リアクティブ関数は使わずに普通の値もオブジェクトも基本的にはレフ関数一つでデータをリアクティブにすること。
    <br />
    <br />
    レフオブジェクトがリアクティブオブジェクトの中ではなくて普通のオブジェクトの中にあった場合のテンプレート内での.valueの動きについても軽く見ていく。
  </h2>
</template>

<style>
.ketsu-ron {
  background-color: red;
  color: white;
}

.kotae {
  color: green;
}
</style>
