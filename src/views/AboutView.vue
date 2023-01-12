<script lang="ts">
export default {
  name: 'about-view'
}
</script>
<script lang="ts" setup>
import {ref} from 'vue'
const testCount = ref(0)
</script>

<template>
  <div class="about">
    <button @click="testCount++">add testCount</button>
    <h1 v-for="item in 100" :key="item">{{ item }}====This is an about page ==== {{ testCount }}</h1>
  </div>
</template>

<style>
h1 {
  border-bottom: 1px solid #ff6700;
}
</style>
