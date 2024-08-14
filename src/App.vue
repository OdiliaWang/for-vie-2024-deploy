<script setup>
import { ref } from 'vue'

const text = ref('這是一段文字')
</script>

<template>
  <div>
    <h1>{{ text }}</h1>
    <input type="text" v-model="text" />
  </div>
</template>
