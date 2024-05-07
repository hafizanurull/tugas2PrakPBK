<template>
  <div>
    <h1 style="color: aqua;">input red atau blue, maka akan berubah warna</h1>
    <input type="text" v-model="inputText" :class="{ 'input-red': isRed, 'input-blue': isBlue }" @input="handleChange">
    <p :style="{ color: textColor }">{{ inputText }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const inputText = ref('')
const isRed = ref(false)
const isBlue = ref(false)
const textColor = ref('black')

const handleChange = () => {
  if (inputText.value === 'red') {
    isRed.value = true
    isBlue.value = false
    textColor.value = 'red'
  } else if (inputText.value === 'blue') {
    isRed.value = false
    isBlue.value = true
    textColor.value = 'blue'
  } else {
    isRed.value = false
    isBlue.value = false
    textColor.value = 'black'
  }
}
</script>

<style scoped>
.input-red {
  border-color: red;
}
.input-blue {
  border-color: blue;
}
</style>
