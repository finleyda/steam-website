<script setup lang="ts">
import { ref } from 'vue'

const isSignedIn = ref(false)

const quickStats = [
  { label: 'Profile status', value: 'Ready' },
  { label: 'Recent games', value: '12' },
  { label: 'Wishlist', value: '7' },
]
</script>

<template>
  <div class="layout">
    <header class="header">
      <div>
        <h1>Steam Checker</h1>
        <p>Discover your Steam activity at a glance</p>
      </div>
      <a class="ghost-btn" :href="'https://steam.tomthurston.dev/auth/steam'" target="_blank" rel="noopener noreferrer">
        {{ isSignedIn ? 'Sign out' : 'Sign in' }}
      </a>
    </header>

    <main class="dashboard">
      <section v-if="!isSignedIn" class="hero-card">
        <div class="hero-copy">
          <p class="eyebrow">Signed out</p>
          <h2>Turn your Steam profile into a polished dashboard</h2>
          <p>
            Welcome back to your personal Steam hub. Sign in to see account details,
            recent activity, and helpful highlights in one place.
          </p>
          <p class="note">
            Note: your Steam privacy settings may limit which profile details and activity data are visible here.
          </p>
        </div>

        <div class="preview-card">
          <h3>Dashboard preview</h3>
          <div v-for="item in quickStats" :key="item.label" class="stat-row">
            <span>{{ item.label }}</span>
            <strong>{{ item.value }}</strong>
          </div>
        </div>
      </section>

      <section v-else class="dashboard-grid">
        <div class="content-box">
          <h3>Welcome back</h3>
          <p>Your dashboard is ready to show account activity, friends, and recent game updates.</p>
        </div>

        <div class="content-box">
          <h3>Quick actions</h3>
          <ul>
            <li>Review your profile summary</li>
            <li>Check your wishlist</li>
            <li>View recent games</li>
          </ul>
        </div>
      </section>
    </main>

    <footer class="footer">
      <p>Steam Website © 2026 — All rights reserved</p>
    </footer>
  </div>
</template>

<style>
.layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: Arial, sans-serif;
}

.header {
  background: #1b2838;
  color: white;
  padding: 1.5rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}

.header h1 {
  margin: 0 0 0.25rem;
}

.header p {
  margin: 0;
  opacity: 0.8;
}

.ghost-btn,
.primary-btn,
.secondary-btn {
  border: none;
  border-radius: 999px;
  padding: 0.75rem 1rem;
  font-weight: 600;
  cursor: pointer;
}

.ghost-btn {
  background: transparent;
  color: white;
  border: 1px solid rgba(255,255,255,0.4);
}

.primary-btn {
  background: #66c0f4;
  color: #08111b;
}

.secondary-btn {
  background: #2a475e;
  color: white;
}

.dashboard {
  flex: 1;
  padding: 2rem;
  background: #f5f5f5;
}

.hero-card {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 1.5rem;
  align-items: center;
}

.hero-copy,
.preview-card,
.content-box {
  background: white;
  border-radius: 12px;
  padding: 1.5rem;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
}

.eyebrow {
  text-transform: uppercase;
  letter-spacing: 0.2em;
  color: #66c0f4;
  font-weight: 700;
  font-size: 0.8rem;
}

.note {
  margin-top: 0.75rem;
  color: #5b6470;
  font-size: 0.95rem;
}

.actions {
  display: flex;
  gap: 0.75rem;
  margin-top: 1rem;
}

.stat-row {
  display: flex;
  justify-content: space-between;
  padding: 0.65rem 0;
  border-bottom: 1px solid #e6e6e6;
}

.stat-row:last-child {
  border-bottom: none;
}

.dashboard-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1.25rem;
}

ul {
  margin: 0.5rem 0 0 1rem;
  padding: 0;
}

.footer {
  background: #1b2838;
  color: white;
  padding: 1rem;
  text-align: center;
}

@media (max-width: 800px) {
  .hero-card,
  .dashboard-grid {
    grid-template-columns: 1fr;
  }

  .header {
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>

