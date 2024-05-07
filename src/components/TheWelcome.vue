<template>
  <div :style="{ background: backgroundColor }">
    <h1 style="color: aqua;">Masukkan 'red' atau 'blue' untuk mengubah warna latar belakang</h1>
    <input type="text" v-model="inputText" @input="handleChange">
    <p :style="{ color: textColor }">{{ inputText }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const inputText = ref('')
const textColor = ref('black')
const backgroundColor = ref('white')

const handleChange = () => {
  if (inputText.value === 'red') {
    textColor.value = 'red'
    backgroundColor.value = 'pink'
  } else if (inputText.value === 'blue') {
    textColor.value = 'blue'
    backgroundColor.value = 'lightblue'
  } else {
    textColor.value = 'black'
    backgroundColor.value = 'white'
  }
}
</script>

<style scoped>
</style>
