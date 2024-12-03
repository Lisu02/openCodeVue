<script setup>
import { ref } from "vue";

// Reaktywne dane dla rejestracji
const username = ref("");
const password = ref("");
const confirmPassword = ref("");

// Funkcja obsługi rejestracji
const handleRegister = () => {
  if (password.value !== confirmPassword.value) {
    alert("Passwords do not match!");
    return;
  }
  console.log("Registering with", {
    username: username.value,
    password: password.value,
  });
  // Tu można dodać logikę do wysyłania danych do API
};
</script>

<template>
  <div class="register-container">
    <h2>Register</h2>
    <form @submit.prevent="handleRegister">
      <div>
        <label for="username">Username</label>
        <input
          id="username"
          v-model="username"
          type="text"
          placeholder="Enter your username"
          required
        />
      </div>
      <div>
        <label for="password">Password</label>
        <input
          id="password"
          v-model="password"
          type="password"
          placeholder="Enter your password"
          required
        />
      </div>
      <div>
        <label for="confirmPassword">Confirm Password</label>
        <input
          id="confirmPassword"
          v-model="confirmPassword"
          type="password"
          placeholder="Confirm your password"
          required
        />
      </div>
      <button type="submit">Register</button>
    </form>
  </div>
</template>

<style scoped>
.register-container {
  max-width: 400px;
  margin: auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
form div {
  margin-bottom: 15px;
}
label {
  display: block;
  font-weight: bold;
  margin-bottom: 5px;
}
input {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}
button {
  padding: 10px 15px;
  background-color: #28a745;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
button:hover {
  background-color: #218838;
}
</style>
