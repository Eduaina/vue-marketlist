<script setup>
import { ref } from 'vue'

const message =ref("My Marketlist")
const show =ref(true)
const list =ref(["bread","eggs","meat"])
</script>

<template>
  <h1 >{{ message }}</h1>
  <div>
    <div>
      <button @click="show = !show">Hide</button>
      <button @click="list.push('air')">Expand</button>
      <button @click="list.pop()">Reduce</button>
   </div>
   <ul v-if="show && list.length">
   <li v-for="item of list">{{ item }}</li>
   </ul>
   <p v-else-if="list.length">You have hidden your market list.</p>
   <p v-else>Nothing to see.</p>
 </div>
</template>

<style>
button, a {
  display: block;
  }
</style>
