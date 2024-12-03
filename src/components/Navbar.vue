<template>
  <nav class="navbar">
    <div class="navbar-logo">
      <a href="/">OpenCode</a>
    </div>
    <ul class="navbar-links">
      <li><a href="/playground">Playground</a></li>
      <li><a href="/task">Tasks</a></li>
      <li><a href="/task/add">AddTask</a></li>
    </ul>
  </nav>
</template>

<script setup>
/* W tym przypadku nie ma potrzeby definiowania żadnej logiki,
   ale możesz tutaj dodawać zmienne, metody lub reaktywną logikę */
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 1rem;
  background-color: #1a6600;
  color: #000000;
}

.navbar-logo a {
  text-decoration: none;
  font-size: 1.5rem;
  font-weight: bold;
  color: #ffffff;
}

.navbar-links {
  list-style: none;
  display: flex;
  margin: 0;
  padding: 0;
}

.navbar-links li {
  margin-left: 1rem;
}

.navbar-links a {
  text-decoration: none;
  color: #fff;
  transition: color 0.3s ease;
}

.navbar-links a:hover {
  color: #66ff00;
}
</style>
