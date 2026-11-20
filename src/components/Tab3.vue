<template>
  <div class="h-64 bg-blue-500 px-10 w-[90%] mx-auto flex justify-center rounded-lg items-center mt-4">
    <h2>Tab 3 Content</h2>
    <p>This is the content for Tab </p>
    <div class="flex">
      <input v-model="inputValue" class="border border-gray-300 rounded-md py-2 px-4 focus:outline-none focus:ring-2 focus:ring-blue-500" type="text" placeholder="Enter text here..." />
    </div>
  </div>
</template>

<script setup>

import { ref } from 'vue'

const inputValue = ref('')

</script>