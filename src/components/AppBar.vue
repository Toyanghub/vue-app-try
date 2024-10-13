<template>
  <!-- Root div element to hold all components -->
  <div>
    <!-- Main App Bar/Navbar -->
    <v-app-bar app color="black" dark>
      <!-- Title of the Navbar -->
      <v-toolbar-title
        ><img src="@/assets/img/logo.png" alt="" srcset=""
      /></v-toolbar-title>
      <v-spacer></v-spacer>
      <!-- Tabs for desktop view -->

      <!-- Show tabs only if not in mobile view  ( v-if="!mobileView"  ) -->

      <v-tabs
        v-if="!mobileView"
        v-model="tab"
        bg-color="black"
        color="white"
        grow
      >
        <!-- Iterate through items array and create tabs -->
        <v-tab
          v-for="item in items"
          :key="item"
          :text="item"
          :value="item"
        ></v-tab>
      </v-tabs>
      <!-- Hamburger menu button for mobile view -->
      <v-btn icon @click="drawer = !drawer" v-else>
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>

    <!-- Navigation Drawer for mobile view -->
    <v-navigation-drawer v-model="drawer" app temporary>
      <v-list>
        <!-- Iterate through items array and create list items -->

        <v-list-item
          v-for="item in items"
          :key="item"
          @click="
            tab = item; // Update tab state when item is clicked
            drawer = false; //Close the drawer
          "
        >
          <v-list-item-title>{{ item }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: "AppBar",
  data() {
    return {
      tab: "Appetizers", // Default selected tab
      items: ["Appetizers", "Entrees", "Deserts", "Cocktails"], // Tab items
      drawer: false, // State to control drawer visibility
      mobileView: false, // State to check if in mobile view
    };
  },
  mounted() {
    this.checkViewport(); // Check viewport on mount
    window.addEventListener("resize", this.checkViewport); // Listen for resize events
  },
  methods: {
    checkViewport() {
      // Method to check viewport size
      this.mobileView = window.innerWidth <= 768; // Set mobileView based on window width
    },
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.checkViewport); // Remove event listener
  },
};
</script>

<style scoped>
.v-app-bar {
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Adds subtle shadow for depth */
}
.v-toolbar-title {
  font-weight: bold;
}
</style>
