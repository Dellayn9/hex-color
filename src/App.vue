<script setup>
import { ref } from 'vue'
function changeColor() {
  let hex_numbers = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'A', 'B', 'C', 'D', 'E', 'F']

  let hexcode = ref('')

  for (let i = 0; i < 6; i++) {
    let random_index = Math.floor(Math.random() * hex_numbers.length)

    hexcode.value += hex_numbers[random_index]
  }

  document.getElementsByTagName('body')[0].style.background = '#' + hexcode.value
}
</script>

<template>
  <div class="min-h-screen flex justify-center items-center">
    <div>
      <h1 class="text-center mb-10" id="hexcode">{{ hexcode }}</h1>
      <button
        @click="changeColor"
        type="button"
        class="p-3 rounded-lg bg-gray-800 hover:bg-gray-900 transition text-white hover:-translate-y-0.5 shadow-lg hover:shadow-xl"
      >
        Жми здесь
      </button>
    </div>
  </div>
</template>

<style scoped></style>
