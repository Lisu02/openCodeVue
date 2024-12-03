<script setup>
import { ref } from "vue";

// Reaktywne dane dla logowania
const username = ref("");
const password = ref("");

// Funkcja obsługi logowania
const handleLogin = () => {
  console.log("Logging in with", {
    username: username.value,
    password: password.value,
  });
  // Tu można dodać logikę do wysyłania danych do API
};
</script>

<template>
  <div class="login-container">
    <h2>Login</h2>
    <form @submit.prevent="handleLogin">
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
      <button type="submit">Login</button>
    </form>
  </div>
</template>

<style scoped>
.login-container {
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
