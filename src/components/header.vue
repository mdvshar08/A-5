<script setup>

</script>

<template>
  <div class="header-buttons">
    <h1>BingeBox</h1>
    <div class="buttons">
      <RouterLink to="/register" class="button register">Register</RouterLink>
      <RouterLink to="/login" class="button login">Login</RouterLink>
    </div>
  </div>
</template>

<style scoped>
h1 {
  color: #e50914;
  font-family: 'Arial', sans-serif;
  font-weight: bold;
  font-size: 2rem;
}

.header-buttons {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  background-color: #141414;
  padding: 10px 20px;
  border-bottom: 2px solid #333333;
}

.buttons {
  display: flex;
  gap: 10px; 
}

.header-buttons .button {
  display: inline-block;
  background-color: #e50914;
  color: #ffffff;
  padding: 10px 30px;
  font-size: 18px;
  text-align: center;
  text-decoration: none;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-weight: bold;
  transition: background-color 0.3s, transform 0.2s;
}

.header-buttons .button:hover {
  background-color: #f40612;
  transform: scale(1.05);
}

body {
  background-color: #000000;
  color: #ffffff;
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}
</style>
