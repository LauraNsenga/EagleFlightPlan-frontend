<template>
  <v-container class="d-flex flex-column align-center justify-center text-center">
    <v-img src="@/assets/eagle-logo.png" max-height="120" contain class="mt-10"></v-img>
    <h1 class="text-h4 font-weight-bold mt-4">Welcome to Eagle Flight Plan</h1>
    <p class="text-subtitle-1 mt-2">Your journey to academic success starts here.</p>

    <v-btn color="primary" class="mt-4" @click="navigateTo('dashboard')">Go to Dashboard</v-btn>
    <v-btn color="secondary" class="mt-2" @click="navigateTo('profile')">View Profile</v-btn>
  </v-container>
</template>

<script setup>
import { useRouter } from "vue-router";

const router = useRouter();

const navigateTo = (route) => {
  router.push({ name: route });
};
</script>

<style scoped>
.v-container {
  min-height: 80vh;
}
</style>
