<template>
    <nav class="navbar">
        <ul class="nav-list">
            <li>
                <a href="/">Home</a>
            </li>

            <li>
                <a href="/about">About</a>
            </li>

            <li>
                <a href="/contact">Contact</a>
            </li>
        </ul>
    </nav>
</template>

<script setup>

</script>

<style scoped>

.navbar {
    background-color: #dc8686;
    padding: 16px 30px;
}

.nav-list {
    list-style: none;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 30px;

    margin: 0;
    padding: 0;
}

.nav-list li a {
    color: white;
    text-decoration: none;
    font-size: 16px;
    font-weight: 600;
    transition: 0.3s;
}

.nav-list li a:hover {
    color: #ffe5e5;
}

</style>