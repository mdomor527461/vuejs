<template>
    <div class="fixed inset-0 z-50 flex items-center justify-center bg-black/50">
        <div class="w-90 max-w-[90vw] rounded-xl bg-white p-6 shadow-xl">
            <div class="flex items-start justify-between mb-2">
                <h2 class="text-lg font-medium">This is a popup</h2>
                <button class="text-gray-400 hover:text-gray-600" @click="emit('close')">✕</button>
            </div>
            <p class="text-sm text-gray-500 mb-6">A short message goes here.</p>
            <div class="flex justify-end gap-2">
                <button class="px-4 py-2 text-sm rounded-lg border hover:bg-gray-50">Cancel</button>
                <button class="px-4 py-2 text-sm rounded-lg bg-gray-900 text-white hover:bg-gray-800" @click="emit('close')">Close</button>
            </div>
        </div>
    </div>
</template>

<script setup>
const emit = defineEmits(['close']);
</script>