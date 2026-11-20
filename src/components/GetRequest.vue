<template>

    <h1>Try GET Request to get data from jsonplaceholder.typecode.com/posts</h1>

    <h1 v-if="loading">Loading...</h1>
    <h1 v-else-if="error">{{ error }}</h1>
    <div v-else>
        <div class="grid grid-cols-3 gap-3">
            <div v-for="post in posts" :key="post.id" class="bg-gray-300 p-4 border rounded">

                <h1 class="text-red-500">post{{post.id  }} title : {{ post.title }}</h1>

                <p class="text-green-500">post{{ post.id }} body :  {{ post.body }}</p>

            </div>
        </div>
    </div>

</template>

<script setup>

import { ref, onMounted } from 'vue';

const posts = ref([]);
const loading = ref(true);
const error = ref(null);


async function getPosts() {

    try {
        const response = await fetch('https://jsonplaceholder.typicode.com/posts')
        if (!response.ok) {
            throw new Error('Some Went Wrong !');
        }
        const data = await response.json();
        posts.value = data.slice(0,9);
        // console.log(posts);

    }
    catch (error) {
        error.value = error.message;
    }
    finally {
        loading.value = false;
    }

}

onMounted(() => {
    getPosts();
})

</script>