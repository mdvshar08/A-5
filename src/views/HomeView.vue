<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
    <div class="hero">
        <div class="overlay">
            <div class="navbar">
                <h1>BingeBox</h1>
                <div class="nav-buttons">
                    <RouterLink to="/register" class="button register">Register</RouterLink>
                    <RouterLink to="/login" class="button login">Login</RouterLink>
                </div>
            </div>
            <div class="hero-content">
                <h2>Watch Anywhere. Cancel Anytime.</h2>
                <p>Ready to watch? Enter your email to create or restart your membership.</p>
                <input type="email" placeholder="Email address" class="email-input">
                <button class="button join">Get Started</button>
            </div>
        </div>
    </div>
</template>

<style scoped>
.hero {
    background-image: url('https://source.unsplash.com/random/1920x1080/?cinema'); /* Updated query */
    background-size: cover;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    box-shadow: inset 0 0 200px rgba(0, 0, 0, 0.6); /* Added dark shadow for extra contrast */
}

.overlay {
    background-color: rgba(0, 0, 0, 0.5); /* Reduced opacity */
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: white;
    text-align: center;
    padding: 20px;
}

.navbar {
    position: absolute;
    top: 15px;
    left: 20px;
    right: 20px;
    display: flex;
    justify-content: space-between;
    padding: 0;
}

.nav-buttons .button {
    background-color: #333; /* Changed color */
    color: white;
    padding: 12px 25px;
    text-decoration: none;
    border-radius: 8px;
    margin-left: 12px;
    font-weight: bold;
    transition: background-color 0.3s ease;
    text-transform: uppercase; /* Added uppercase text */
}

.nav-buttons .button:hover {
    background-color: #555; /* Darker hover effect */
}

.hero-content {
    text-align: center;
    margin-top: 30px;
}

.hero-content h2 {
    font-size: 3.5rem; /* Increased font size */
    margin-bottom: 25px;
    font-family: 'Arial', sans-serif; /* Changed font */
    letter-spacing: 1.5px; /* Added letter-spacing */
}

.hero-content p {
    font-size: 1.5rem; /* Increased font size */
    margin-bottom: 20px;
    font-family: 'Arial', sans-serif;
}

.email-input {
    padding: 12px;
    width: 350px;
    border-radius: 8px;
    border: 1px solid #ccc;
    margin-bottom: 15px;
    font-size: 1.1rem;
}

.join {
    background-color: #e50914;
    color: white;
    padding: 12px 28px;
    border: none;
    border-radius: 8px;
    font-size: 1.1rem;
    cursor: pointer;
    font-weight: bold;
    transition: background-color 0.3s ease;
}

.join:hover {
    background-color: #f40612;
}
</style>
