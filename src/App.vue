<script setup>
import { ref } from 'vue'
const texto = ref('')
</script>

<template>
  <div>
        <input type="text" v-model="texto" />
        <p>Texto digitado: {{ texto }}</p>
    </div>
</template>

<style scoped>

</style>
