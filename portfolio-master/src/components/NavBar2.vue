<template>
    <v-app-bar app color="black" dark flat class="px-12" >
      <v-btn >
        <!-- <v-icon color="blue" left class="mr-2">fas fa-signature</v-icon> ZOLENA -->
        <v-icon color="blue" left class="mr-2">fas fa-yin-yang</v-icon> ZOLENA
        
      </v-btn>
      
  
      <v-spacer></v-spacer>
      <v-btn text @click="$router.push('/')" class="text-blue">Home</v-btn>
      <v-btn text @click="$router.push('/contact')">Contact</v-btn>
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
  
  <style>
  </style>