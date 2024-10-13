<template>
  <v-app>
    <AppBar />
    <v-main>
      <Carousel />
      <Tabs />
      <AboutUs />
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
import Carousel from "./components/Carousel.vue";
import Tabs from "./components/Tabs.vue";
import AboutUs from "./components/AboutUs.vue"; // Import AboutUs component
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
