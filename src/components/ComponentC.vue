<template>
    <h1>This is Component C</h1>
    <h1>User name : {{ userName }}</h1>
</template>
<script setup>
import {inject} from 'vue'

const userName = inject('userName')
</script>