<script setup lang="ts">
import { ref } from 'vue';

const rand1 = ref(Math.random() * 1000)
const rand2 = ref(Math.random() * 1000)
const rand3 = ref(Math.random() * 100)

const rand4 = ref(Math.random() * 100)

function update() {
  setTimeout(() => {
    rand1.value = Math.random() * 1000
    rand2.value = Math.random() * 1000
    rand3.value = Math.random() * 200
    rand4.value = Math.random() * 4000
    update()
  }, rand4.value)
}

update()
console.log()
</script>

<template>
  <svg viewBox="0 0 1000 1000" version="1.1" xmlns="http://www.w3.org/2000/svg"
    :style="`background-color:rgb(${Math.random() * 255},${Math.random() * 255},${Math.random() * 255})`">
    <circle :cx="rand1" :cy="rand2" :r="rand3" :fill="`rgb(${rand1},${rand2},${rand3})`" />
  </svg>
</template>

<style>
* {
  margin: 0;
  transition: 3s all;
}

svg {
  height: 99vh;
  width: 100vw;

}
</style>
