<script setup>

</script>

<template>
    <h1 class="hero">BingeBox</h1>
    <RouterLink to="/Login" class="button register">Login</RouterLink>
    <RouterLink to="/" class="button home">Back to Home</RouterLink>

    <div class="form-container">
        <h2>Register Account</h2>
        <form @submit.prevent="handleLogin">
            <input type="text" placeholder="First Name" class="input-field" required>
            <input type="text" placeholder="Last Name" class="input-field" required>
            <input type="email" placeholder="Email" class="input-field" required />
            <input v-model="password" type="password" placeholder="Password" class="input-field" required />
            <input v-model="reEnterPassword" type="password" placeholder="Re-enter Password" class="input-field"
                required />
            <button type="submit" class="button login">Login</button>
        </form>
    </div>
</template>

<style scoped>
body {
    background-color: #141414; /* Dark gray for the background */
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    padding: 20px 0 70px;
    color: #ffffff; /* White text for readability */
}

.hero {
    background-color: #141414; /* Match the body background */
    color: #ffffff; /* White text for contrast */
    text-align: center;
    padding: 60px 20px;
    margin-bottom: 20px;
}

.hero h1 {
    font-size: 60px;
    color: #e50914; /* Netflix red for heading */
    margin-bottom: 10px;
    font-weight: bold; /* Bold for emphasis */
}

.hero p {
    font-size: 20px;
    margin-bottom: 20px;
    color: #d3d3d3; /* Light gray for descriptive text */
}

.form-container {
    background-color: #222222; /* Darker gray for the form container */
    border-radius: 10px;
    padding: 40px 20px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.6); /* Stronger shadow for depth */
    max-width: 400px;
    margin: 0 auto;
}

.form-container h2 {
    color: #e50914; /* Netflix red for form headings */
    text-align: center;
    font-size: 28px;
    margin-bottom: 30px;
    font-weight: bold;
}

.input-field {
    width: 100%;
    padding: 12px;
    margin-bottom: 15px;
    border: 2px solid #333333; /* Subtle dark gray border */
    border-radius: 5px;
    font-size: 16px;
    color: #ffffff; /* White text for input fields */
    background-color: #141414; /* Dark gray background for input fields */
}

.input-field:focus {
    border-color: #e50914; /* Netflix red for focus effect */
    outline: none;
}

.button {
    background-color: #e50914; /* Netflix red for buttons */
    color: #ffffff; /* White text for contrast */
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
    background-color: #f40612; /* Brighter red for hover effect */
    transform: scale(1.05); /* Subtle scaling on hover */
}

footer {
    background-color: #141414; /* Match the body background */
    color: #d3d3d3; /* Light gray for footer text */
    text-align: center;
    padding: 10px;
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    border-top: 2px solid #333333; /* Subtle border for separation */
}
</style>
