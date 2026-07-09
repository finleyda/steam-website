<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="app-layout">
    <!-- HEADER -->
    <header class="header">
      <h1>Steam Website</h1>
      <p>Edit src/App.vue to change this layout</p>
    </header>

    <!-- MAIN DASHBOARD AREA -->
    <main class="dashboard">
      <h2>Main Dashboard</h2>
      <p>This is where your dashboard content will go.</p>

      <!-- Keep your existing Vite starter text -->
      <section class="starter">
        <p>Get started by editing <code>src/App.vue</code></p>
        <p>Count is 17</p>
        <a href="https://vitejs.dev">Vite Docs</a>
      </section>
    </main>

    <!-- FOOTER -->
    <footer class="footer">
      <p>Steam Website © 2024 — All rights reserved</p>
    </footer>
  </div>
</template>

<style>
.app-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: Arial, sans-serif;
}

/* HEADER */
.header {
  background: #1b2838;
  color: white;
  padding: 1.5rem;
  text-align: center;
}

/* MAIN DASHBOARD */
.dashboard {
  flex: 1;
  padding: 2rem;
  background: #f5f5f5;
}

.starter {
  margin-top: 2rem;
  padding: 1rem;
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

/* FOOTER */
.footer {
  background: #1b2838;
  color: white;
  padding: 1rem;
  text-align: center;
}
</style>


