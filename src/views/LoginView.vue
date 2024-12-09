<script setup>
import { RouterLink, useRouter } from 'vue-router';
import { ref } from 'vue';

const router = useRouter();
const password = ref('');

const handleLogin = () => {
    if (password.value === "madhav") {
        router.push("/movies");
    } else {
        alert("Invalid Password");
    }
};
</script>

<template>
    <h1 class="hero">BingeBox</h1>
    <RouterLink to="/register" class="button register">Register</RouterLink>
    <RouterLink to="/" class="button home">Back to Home</RouterLink>

    <div class="form-container">
        <h2>Login to Your Account</h2>
        <form @submit.prevent="handleLogin">
            <input type="email" placeholder="Email" class="input-field" required />
            <input v-model="password" type="password" placeholder="Password" class="input-field" required />
            <button type="submit" class="button login">Login</button>
        </form>
    </div>
</template>

<style scoped>
body {
    background-color: #141414;
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    padding: 20px 0 70px;
    color: #ffffff;
}

.hero {
    background-color: #141414;
    color: #ffffff;
    text-align: center;
    padding: 60px 20px;
    margin-bottom: 20px;
}

.hero h1 {
    font-size: 60px;
    color: #e50914;
    margin-bottom: 10px;
    font-weight: bold;
}

.hero p {
    font-size: 20px;
    margin-bottom: 20px;
    color: #d3d3d3;
}

.form-container {
    background-color: #222;
    border-radius: 10px;
    padding: 40px 20px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.6);
    max-width: 400px;
    margin: 0 auto;
}

.form-container h2 {
    color: #e50914;
    text-align: center;
    font-size: 28px;
    margin-bottom: 30px;
    font-weight: bold;
}

.input-field {
    width: 80%; 
    padding: 10px; 
    margin-bottom: 15px;
    border: 2px solid #333;
    border-radius: 5px;
    font-size: 14px;
    color: #ffffff;
    background-color: #141414;
    display: block;
    margin-left: auto;
    margin-right: auto;
}

.input-field:focus {
    border-color: #e50914;
    outline: none;
}

.button {
    background-color: #e50914;
    color: #ffffff;
    padding: 12px 30px;
    font-size: 18px;
    border: none;
    margin-top: 10px;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.2s;
    width: 100%;
    font-weight: bold;
}

.button:hover {
    background-color: #f40612;
    transform: scale(1.05);
}

footer {
    background-color: #141414;
    color: #d3d3d3;
    text-align: center;
    padding: 10px;
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    border-top: 2px solid #333;
}
</style>