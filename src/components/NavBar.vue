<template>
  <v-app-bar app color="blue" dark flat class="px-12">
    <v-btn @click="scroll('home')">
      <v-icon color="white" left class="mr-2">fas fa-dragon</v-icon>Lorem
    </v-btn>
    <v-spacer></v-spacer>
    <v-btn text @click="scroll('home')" class="text-white">Home</v-btn>
    <v-btn text @click="scroll('about')">About</v-btn>
    <v-btn text @click="scroll('projects')">Projects</v-btn>
    <!-- <v-btn text @click="scroll('services')">Services</v-btn> -->
    <!-- <v-btn text @click="scroll('page')">Page</v-btn> -->
    <!-- <v-btn text @click="scroll('blog')">Blog</v-btn> -->
    <v-btn text @click="scroll('contact')">Contact</v-btn>
  </v-app-bar>
</template>

<script>
export default {
  methods: {
    scroll(refName) {
      const element = document.getElementById(refName);
      element.scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>
