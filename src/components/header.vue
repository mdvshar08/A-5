<script setup>

</script>

<template>
  <div class="header-buttons">
    <RouterLink to="/register" class="button register">Register</RouterLink>
    <RouterLink to="/login" class="button login">Login</RouterLink>
    <h1>BingeBox</h1>
  </div>
</template>

<style scoped>
h1 {
  margin-left: auto;
  padding: 1%;
  color: #e50914; /* Netflix's signature red color */
  font-family: 'Arial', sans-serif;
  font-weight: bold;
}

.header-buttons {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  background-color: #141414; /* Dark gray background similar to Netflix */
  padding: 10px 20px;
  border-bottom: 2px solid #333333; /* Subtle border for separation */
}

.button {
  margin-right: 10px;
}

.header-buttons .button {
  display: inline-block;
  background-color: #e50914; /* Netflix red for buttons */
  color: #ffffff; /* White text for contrast */
  padding: 10px 30px;
  font-size: 18px;
  text-align: center;
  text-decoration: none;
  border: none;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  font-weight: bold;
  transition: background-color 0.3s, transform 0.2s;
}

.header-buttons .button:hover {
  background-color: #f40612; /* Slightly brighter red on hover */
  transform: scale(1.05); /* Subtle hover scaling */
}

body {
  background-color: #000000; /* Black background for the entire page */
  color: #ffffff; /* White text for readability */
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}
</style>
