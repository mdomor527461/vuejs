<script setup>
import {
    ref,
    onBeforeMount,
    onMounted,
    onBeforeUpdate,
    onUpdated,
    onBeforeUnmount,
    onUnmounted
} from 'vue'

const count = ref(0)

onBeforeMount(() => {
    console.log('1. Before Mount')
})

onMounted(() => {
    console.log('2. Mounted')
})

onBeforeUpdate(() => {
    console.log('3. Before Update')
})

onUpdated(() => {
    console.log('4. Updated')
})

onBeforeUnmount(() => {
    console.log('5. Before Unmount')
})

onUnmounted(() => {
    console.log('6. Unmounted')
})
</script>

<template>
    <h1>{{ count }}</h1>

    <button @click="count++">
        Increase
    </button>
</template>