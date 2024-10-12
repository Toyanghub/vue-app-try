<template>
  <v-app>
    <AppBar />
    <v-main>
      <Carousel />
      <v-container class="white-background" fluid>
        <v-row align="center" justify="center" class="fill-height">
          <v-col cols="12" md="8">
            <v-btn color="primary">Welcome to My App</v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import AppBar from "./components/AppBar.vue";
</script>

<style scoped>
.white-background {
  background-color: white;
  min-height: 100vh; /* Ensures it takes full screen height */
}
.fill-height {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
