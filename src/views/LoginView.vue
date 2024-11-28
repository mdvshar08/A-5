<script setup>
import { RouterLink, useRouter } from 'vue-router';
import { ref } from 'vue';

const router = useRouter();
const password = ref('');

const handleLogin = () => {
  if (password.value === "123") {
    router.push("/movies");
  } else {
    alert("Invalid Password");
  }
};
</script>

<template>
  <div class="hero">
    <div class="overlay">
      <div class="navbar">
        <h1>BingeBox</h1>
        <RouterLink to="/register" class="button register">Register</RouterLink>
      </div>
      <div class="form-container">
        <h2>Login to Your Account</h2>
        <form @submit.prevent="handleLogin">
          <input type="email" placeholder="Email" class="input-field" required />
          <input v-model:="password" type="password" placeholder="Password" class="input-field" required />
          <button type="submit" class="button login">Login</button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.hero {
  background-image: url('https://source.unsplash.com/random/1920x1080/?cinema');
  background-size: cover;
  background-position: center;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.hero::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.4); /* Added a gradient overlay for smoother contrast */
}

.overlay {
  position: relative;
  color: white;
  text-align: center;
  z-index: 1;
  padding: 20px;
}

.navbar {
  position: absolute;
  top: 20px;
  left: 20px;
  right: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 2;
  font-family: 'Arial', sans-serif;
}

.navbar h1 {
  font-size: 2.5rem;
  font-weight: bold;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: #fff;
  margin: 0;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.4); /* Added text shadow for better visibility */
}

.navbar .register {
  background-color: #e50914;
  color: white;
  padding: 12px 28px;
  text-decoration: none;
  border-radius: 8px;
  font-size: 1.1rem;
  font-weight: bold;
  transition: background-color 0.3s, transform 0.2s ease-in-out, box-shadow 0.3s ease-in-out;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3); /* Subtle shadow for better depth */
}

.navbar .register:hover {
  background-color: #f40612;
  transform: scale(1.05);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.4); /* Increased shadow on hover */
}

.form-container {
  text-align: center;
  margin-top: 50px;
  color: white;
}

.form-container h2 {
  font-size: 3rem;
  margin-bottom: 25px;
  font-weight: bold;
  letter-spacing: 1.5px;
}

.input-field {
  padding: 15px;
  width: 320px;
  border-radius: 8px;
  border: 1px solid #ccc;
  margin-bottom: 20px;
  font-size: 1rem;
  transition: border-color 0.3s, box-shadow 0.3s ease-in-out;
  outline: none;
}

.input-field:focus {
  border-color: #e50914;
  box-shadow: 0 0 10px rgba(229, 9, 20, 0.6); /* Glow effect on focus */
}

.login {
  background-color: #e50914;
  color: white;
  padding: 12px 24px;
  border: none;
  border-radius: 8px;
  font-size: 1.1rem;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.3s ease-in-out, box-shadow 0.2s;
  font-weight: bold;
}

.login:hover {
  background-color: #f40612;
  transform: scale(1.05);
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3); /* Added shadow to button on hover */
}

@media (max-width: 768px) {
  .hero {
    background-position: top center; /* Adjusted for better mobile positioning */
  }

  .navbar h1 {
    font-size: 2rem; /* Smaller navbar heading on mobile */
  }

  .input-field {
    width: 80%; /* Make input fields responsive on mobile */
  }

  .form-container h2 {
    font-size: 2.5rem; /* Smaller form heading for mobile */
  }

  .navbar .register {
    padding: 10px 22px; /* Adjust register button size */
  }

  .login {
    padding: 10px 20px; /* Adjust login button size */
  }
}

@media (max-width: 480px) {
  .navbar h1 {
    font-size: 1.6rem; /* Further reduce navbar heading size for small screens */
  }

  .input-field {
    width: 90%; /* Maximize input field width on very small screens */
  }

  .form-container h2 {
    font-size: 2rem; /* Even smaller heading on mobile */
  }

  .navbar .register {
    padding: 8px 18px; /* Smaller register button for very small screens */
  }

  .login {
    padding: 8px 18px; /* Smaller login button for very small screens */
  }
}
</style>
 