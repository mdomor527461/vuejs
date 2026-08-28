<template>
    <div class="form-wrapper">

        <form class="form-card" @submit.prevent="submitForm">

            <div class="form-header">
                <h2>Create Account</h2>
                <p>Please enter your information below</p>
            </div>

            <!-- Name -->
            <div class="form-group">
                <label for="name">Name</label>

                <input
                    id="name"
                    type="text"
                    v-model="name"
                    placeholder="Enter your name"
                />
            </div>

            <!-- Email -->
            <div class="form-group">
                <label for="email">Email</label>

                <input
                    id="email"
                    type="email"
                    v-model="email"
                    placeholder="Enter your email"
                />
            </div>

            <!-- Password -->
            <div class="form-group">
                <label for="password">Password</label>

                <input
                    id="password"
                    type="password"
                    v-model="password"
                    placeholder="Enter your password"
                />
            </div>

            <!-- Submit -->
            <button type="submit" class="submit-btn">
                Submit
            </button>

        </form>

    </div>
</template>

<script setup>
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const password = ref('')

const submitForm = () => {
    console.log('Name:', name.value)
    console.log('Email:', email.value)
    console.log('Password:', password.value)
}
</script>

<style scoped>

* {
    box-sizing: border-box;
}

.form-wrapper {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
    background: #f4f6f9;
}

.form-card {
    width: 100%;
    max-width: 450px;
    background: white;
    padding: 35px;
    border-radius: 14px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
}

.form-header {
    text-align: center;
    margin-bottom: 30px;
}

.form-header h2 {
    margin: 0 0 8px;
    font-size: 28px;
    color: #222;
}

.form-header p {
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
    border: 1px solid #d9dce1;
    border-radius: 8px;
    font-size: 15px;
    outline: none;
    transition: 0.2s;
}

.form-group input:focus {
    border-color: #6366f1;
    box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.12);
}

.form-group input::placeholder {
    color: #aaa;
}

.submit-btn {
    width: 100%;
    padding: 13px;
    margin-top: 5px;
    border: none;
    border-radius: 8px;
    background: #6366f1;
    color: white;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    transition: 0.2s;
}

.submit-btn:hover {
    background: #4f46e5;
    transform: translateY(-1px);
}

.submit-btn:active {
    transform: translateY(0);
}

@media (max-width: 500px) {

    .form-card {
        padding: 25px 20px;
    }

    .form-header h2 {
        font-size: 24px;
    }
}

</style>