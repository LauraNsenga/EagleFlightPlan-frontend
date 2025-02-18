<template>
  <v-container class="fill-height" fluid>
    <v-row align="center" justify="center">
      <v-col cols="12" sm="8" md="4">
        <v-card class="elevation-12">
          <v-card-title class="text-center">
            <v-img
              class="mx-auto my-4"
              :src="logoURL"
              height="300"
              width="100"
              contain
            ></v-img>
            <h1 class="text-h5 mb-2">Eagle Flight Plan</h1>
          </v-card-title>

          <v-card-text class="text-center">
            <SocialLogin />
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import ocLogo from "/oc-logo-white.png";
import { ref, onMounted } from "vue";
import SocialLogin from '../components/SocialLogin.vue';
import { useRouter } from 'vue-router';
import Utils from '../config/utils';

const router = useRouter();
const logoURL = ref("");

onMounted(() => {
  logoURL.value = ocLogo;
  
  // Check if user is already logged in
  const user = Utils.getStore("user");
  if (user) {
    router.push({ name: "home" });
  }
});
</script>

<style scoped>
.v-container {
  background-color: #f5f5f5;
}

.v-card {
  border-radius: 20px;
}
</style>