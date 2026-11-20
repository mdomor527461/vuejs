
<template>
    <h1 class="mt-10 text-indigo-700 text-4xl font-bold text-center mb-10">
        Post Request
    </h1>

    <form @submit.prevent="submitForm" class="mt-10 mb-10">

        <label for="name">Name</label>
        <input type="text" id="name" v-model="form.name" required>

        <label for="email">Email</label>
        <input type="email" id="email" v-model="form.email" required>

        <label for="phone">Phone</label>
        <input type="text" id="phone" v-model="form.phone" required>

        <label for="age">Age</label>
        <input type="number" id="age" v-model.number="form.age" required>

        <label for="salary">Salary</label>
        <input type="number" id="salary" v-model.number="form.salary" required>

        <button type="submit" :disabled="loading">
            {{ loading ? 'Submitting...' : 'Register' }}
        </button>

        <p v-if="successMessage" class="text-green-600">
            {{ successMessage }}
        </p>

        <p v-if="error" class="text-red-600">
            {{ error }}
        </p>

    </form>
</template>

<script setup>
import { ref } from 'vue';

const form = ref({
    name: '',
    email: '',
    phone: '',
    age: null,
    salary: null
});

const loading = ref(false);
const successMessage = ref('');
const error = ref(null);

async function submitForm() {

    loading.value = true;
    successMessage.value = '';
    error.value = null;

    try {

        const response = await fetch(
            'https://jsonplaceholder.typicode.com/posts',
            {
                method: 'POST',

                headers: {
                    'Content-Type': 'application/json'
                },

                body: JSON.stringify(form.value)
            }
        );

        if (!response.ok) {
            throw new Error('Something Went Wrong!');
        }

        const data = await response.json();

        console.log('Server Response:', data);

        successMessage.value = 'Form Submitted Successfully!';

        // Reset form
        form.value = {
            name: '',
            email: '',
            phone: '',
            age: null,
            salary: null
        };

    }
    catch (err) {

        error.value = err.message;

    }
    finally {

        loading.value = false;

    }

}
</script>
