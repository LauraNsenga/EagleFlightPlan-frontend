<script setup>
import MenuBar from "./components/MenuBar.vue";
</script>

<template>
  <v-app>
    <MenuBar :key="$route.fullPath" />
    <v-main class="main-content">
      <v-container fluid>
        <router-view />
      </v-container>
    </v-main>
    <v-footer class="footer" app>
    <span>&copy; {{ new Date().getFullYear() }} Eagle Flight Plan</span>
  </v-footer>
  </v-app>
</template>

<style scoped>
.main-content {
  background-color: #f5f5f5;
  min-height: 100vh;
  padding-top: 2rem;
}

.footer {
  background-color: #8E2232;
  color: white;
  text-align: center;
  padding: 1rem;
}

/* Add some global styles for v-container if needed */
:deep(.v-container) {
  max-width: 1200px;
  margin: 0 auto;
}

/* Optional: Add some responsive padding */
@media (max-width: 960px) {
  .main-content {
    padding-top: 1rem;
  }
  
  :deep(.v-container) {
    padding: 0 1rem;
  }
}
</style>