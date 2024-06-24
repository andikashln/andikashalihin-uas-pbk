<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="header">
      <q-toolbar>
        <q-btn flat round dense icon="menu" @click="drawer = true" class="text-white"/>
        <q-toolbar-title>
          <q-avatar>
            <img :src="logo" alt="Logo">
          </q-avatar>
          CUACA KITA
        </q-toolbar-title>
        <q-space />
        <q-input round dense outlined placeholder="Search..." v-model="searchQuery" class="search-bar" />
        <q-btn flat round dense icon="brightness_6" @click="toggleDarkMode" class="text-white"/>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="drawer" show-if-above bordered class="drawer">
      <q-list>
        <q-item clickable tag="router-link" to="/">
          <q-item-section>
            <q-item-label>Home</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="router-link" to="/tugas1">
          <q-item-section>
            <q-item-label>Tugas 1</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="router-link" to="/tugas2">
          <q-item-section>
            <q-item-label>Tugas 2</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="router-link" to="/tugas3">
          <q-item-section>
            <q-item-label>Tugas 3</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="router-link" to="/tugas4">
          <q-item-section>
            <q-item-label>Tugas 4</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="router-link" to="/tugas5">
          <q-item-section>
            <q-item-label>Tugas 5</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="router-link" to="/tugas6">
          <q-item-section>
            <q-item-label>Tugas 6</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container class="no-scroll">
      <router-view />
    </q-page-container>

    <q-footer elevated class="footer">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img :src="logo" alt="Logo">
          </q-avatar>
        </q-toolbar-title>
        <div class="text-center q-ml-auto footer-content">
          <div>&copy; 2024 Andika Shalihin</div>
          <div class="social-icons">
            <q-icon name="mdi-facebook" @click="openLink('https://www.facebook.com')" />
            <q-icon name="mdi-twitter" @click="openLink('https://www.twitter.com')" />
            <q-icon name="mdi-instagram" @click="openLink('https://www.instagram.com')" />
          </div>
        </div>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
import logo from './assets/logo.png';

export default {
  data() {
    return {
      logo,
      drawer: false,
      searchQuery: '',
      darkMode: false,
    };
  },
  methods: {
    toggleDarkMode() {
      this.darkMode = !this.darkMode;
      document.body.classList.toggle('dark', this.darkMode);
    },
    openLink(url) {
      window.open(url, '_blank');
    },
  },
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Avenir:wght@300;400;700&display=swap');
@import url('https://cdn.jsdelivr.net/npm/@mdi/font/css/materialdesignicons.min.css');

body.dark {
  --q-bg-page: #121212;
  --q-color-page: #ffffff;
}

.header,
.footer {
  backdrop-filter: blur(10px);
}

.q-toolbar-title {
  display: flex;
  align-items: center;
}

.q-toolbar-title q-avatar img {
  width: 40px;
  height: 40px;
}

.search-bar {
  margin-right: 16px;
}

.text-center {
  text-align: center;
}

.q-page {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 0;
}

.q-page-container {
  overflow: hidden;
}

.social-icons {
  display: flex;
  gap: 10px;
  margin-top: 10px;
}

.social-icons q-icon {
  font-size: 24px;
  cursor: pointer;
  transition: color 0.3s, transform 0.3s;
}

.social-icons q-icon:hover {
  color: #ff4081;
  transform: scale(1.2);
}

.q-layout {
  background: linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(128, 0, 128, 0.8));
  background-image: url('./assets/cuaca.jpg');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}

.q-btn.search-btn .q-btn__content {
  text-transform: none;
}

.drawer {
  background-color: var(--q-bg-page);
  color: var(--q-color-page);
}

.footer-content {
  display: flex;
  flex-direction: column;
  align-items: center;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
