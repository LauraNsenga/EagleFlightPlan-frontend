<template>
    <div>
      <MenuBar />
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-col cols="12" sm="10" md="8">
            <v-card class="elevation-2">
              <v-card-title class="text-h5">
                Welcome to Eagle Flight Plan
              </v-card-title>
              <v-card-text>
                <p>Welcome {{ userName }}! Your flight plan journey begins here.</p>
                <!-- Add more content for your home page -->
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  import MenuBar from '../components/MenuBar.vue';
  import Utils from '../config/utils';
  
  const userName = ref('');
  
  onMounted(() => {
    const user = Utils.getStore('user');
    if (user) {
      userName.value = `${user.fName} ${user.lName}`;
    }
  });
  </script>