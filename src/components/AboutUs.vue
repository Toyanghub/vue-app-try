<template>
  <v-container class="about-us">
    <v-row justify="center">
      <v-col cols="12" md="8">
        <v-card>
          <v-card-title class="headline text-center">About Us</v-card-title>
          <v-card-text>
            <p class="text-center">
              We are passionate about creating amazing web experiences that
              drive results. Our team of experts is committed to delivering
              high-quality services to help you succeed online.
            </p>
            <v-divider></v-divider>
            <v-row class="team-section">
              <v-col cols="12" md="4" v-for="member in team" :key="member.name">
                <v-card class="team-card">
                  <v-img :src="member.photo" height="150px" cover></v-img>
                  <v-card-title class="team-name">{{
                    member.name
                  }}</v-card-title>
                  <v-card-subtitle class="team-role">{{
                    member.role
                  }}</v-card-subtitle>
                  <v-card-text>{{ member.bio }}</v-card-text>
                </v-card>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "AboutUs",
  data() {
    return {
      team: [
        {
          name: "John Doe",
          role: "CEO",
          bio: "John leads the company with a vision for innovation and excellence.",
          photo: "https://via.placeholder.com/150",
        },
        {
          name: "Jane Smith",
          role: "CTO",
          bio: "Jane is the tech genius, making sure our services are top-notch.",
          photo: "https://via.placeholder.com/150",
        },
        {
          name: "Paul Brown",
          role: "COO",
          bio: "Paul ensures that operations run smoothly every day.",
          photo: "https://via.placeholder.com/150",
        },
      ],
    };
  },
};
</script>

<style scoped>
.about-us {
  padding: 2rem;
}
.team-section {
  margin-top: 2rem;
}
.team-card {
  text-align: center;
}
.team-name {
  font-weight: bold;
}
.team-role {
  color: grey;
}
</style>
