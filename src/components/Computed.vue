<template>
    <div class="page">
        <div class="card">

            <div class="header">
                <h1>Computed Properties</h1>
                <p>Learn computed properties with Getter & Setter</p>
            </div>

            <!-- Name Inputs -->
            <div class="form-group">
                <label for="firstName">First Name</label>

                <input
                    id="firstName"
                    type="text"
                    v-model="firstName"
                    placeholder="Enter first name"
                />
            </div>

            <div class="form-group">
                <label for="lastName">Last Name</label>

                <input
                    id="lastName"
                    type="text"
                    v-model="lastName"
                    placeholder="Enter last name"
                />
            </div>

            <!-- Result -->
            <div class="result">
                <span>First Name</span>
                <strong>{{ firstName }}</strong>

                <span>Last Name</span>
                <strong>{{ lastName }}</strong>

                <span>Full Name</span>
                <strong>{{ fullName }}</strong>
            </div>

            <!-- Full Name Setter -->
            <div class="form-group">
                <label for="fullName">Change Full Name</label>

                <input
                    id="fullName"
                    type="text"
                    v-model="fullName"
                    placeholder="Enter full name"
                />

                <small>
                    Changing this value will update First Name and Last Name.
                </small>
            </div>

        </div>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const firstName = ref('')
const lastName = ref('')

const fullName = computed({

    // Getter
    get() {
        return `${firstName.value} ${lastName.value}`.trim()
    },

    // Setter
    set(value) {
        const parts = value.trim().split(/\s+/)

        firstName.value = parts[0] || ''
        lastName.value = parts.slice(1).join(' ')
    }

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
    box-sizing: border-box;
}

.form-group input:focus {
    border-color: #dc8686;
    box-shadow: 0 0 0 3px rgba(220, 134, 134, 0.15);
}

.result {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    padding: 20px;
    margin: 25px 0;
    background: #fff5f5;
    border-radius: 10px;
}

.result span {
    color: #777;
    font-size: 14px;
}

.result strong {
    color: #333;
    text-align: right;
    word-break: break-word;
}

.result strong:last-child {
    color: #dc6868;
    font-size: 17px;
}

small {
    display: block;
    margin-top: 7px;
    color: #888;
    font-size: 12px;
}

</style>