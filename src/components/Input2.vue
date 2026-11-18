<template>
    <div>
      
      <input
        type="text"
        v-model="inputValue2"
        />
        <p>You typed: {{ inputValue2  }}</p>
    </div>
</template>

<script setup>
import { ref } from 'vue'
const inputValue2 = ref('')
</script>