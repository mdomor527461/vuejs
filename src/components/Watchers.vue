<template>
    <div class="page">
        <div class="card">
            <div class="header">
                <h1>Watchers</h1>
                <p>Learn how to use watchers in Vue</p>
            </div>

            <div class="form-group">
                <label for="input">Input</label>
                <input
                    id="input"
                    type="text"
                    v-model="inputValue"
                    placeholder="Enter some text"
                />
            </div>

            <div class="result">
                <p>Input Value: {{ inputValue }}</p>
                <p>Debounced Value: {{ debouncedValue }}</p>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, watch, watchEffect } from 'vue'

const inputValue = ref('')
const debouncedValue = ref('')

// Watch for changes in inputValue
watch(inputValue, (newVal, oldVal) => {
    console.log(`Input value changed from ${oldVal} to ${newVal}`)
})

// Watch with immediate option
watch(inputValue, (newVal) => {
    debouncedValue.value = newVal
}, { immediate: true })

// WatchEffect (reactive)
watchEffect(() => {
    console.log(`Input value is now: ${inputValue.value}`)
})
</script>

<style scoped>
.page {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 30px;
    background: #f4f6f8;
}

.card {
    width: 100%;
    max-width: 500px;
    padding: 35px;
    background: white;
    border-radius: 16px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
}

.header {
    text-align: center;
    margin-bottom: 30px;
}

.header h1 {
    margin: 0 0 8px;
    font-size: 28px;
    color: #222;
}

.header p {
    margin: 0;
    color: #777;
    font-size: 14px;
}

.form-group {
    margin-bottom: 20px;
}

.form-group label {
    display: block;
    margin-bottom: 8px;
    font-size: 14px;
    font-weight: 600;
    color: #333;
}

.form-group input {
    width: 100%;
    padding: 12px 14px;
    border: 1px solid #ddd;
    border-radius: 8px;
    font-size: 15px;
    outline: none;
    transition: 0.2s;
   
}

.form-group input:focus {
    border-color: #dc8686;
    box-shadow: 0 0 5px rgba(220, 134, 134, 0.5);
}
</style>