<template>
    <v-app id="contact">
    <NavBar />
    <v-container fluid>
    <v-col cols="12" sm="12" class="px-16" id="contact">
      <v-row>
        <v-row>
        <v-col cols="12" sm="4">
          <div class="child">
            <h1>Contact info.</h1>
            <v-btn
              icon="fas fa-map-marker-alt"
              color=""
              class="mt-10"
              variant="outlined"
            ></v-btn>
            <br />
            <span class="text-caption">Gdańsk, Poland </span>
            <br />
            <span class="text-caption">Aleja Grunwaldzka 82 </span>
            <br />
            <v-btn
              icon="fas fa-phone-alt"
              color=""
              class="mt-10"
              variant="outlined"
            ></v-btn>
            <br />
            <span class="text-caption">736-482-937 </span> <br />
            <span class="text-caption">938-472-635 </span> <br />
            <v-btn
              icon="fas fa-envelope"
              color=""
              class="mt-10"
              variant="outlined"
            ></v-btn>
            <br />
            <span class="text-caption">zofiaassg@gmail.com </span> <br />
            <span class="text-caption">alena.mi@gmail.com </span> <br />
          </div>
        </v-col>
        <v-col cols="12 lowered" sm="8 lowered">
          <h1 class="mt-8 lowered">Send your message</h1>
          <v-divider class="lowered"></v-divider>
          <span class="text-caption"
            >If you need a website designed or developed, feel free to send us a message!
            We would be happy to discuss your project and provide you with a quote. Contact us today to get started!</span
          >
          <form action="https://getform.io/f/d15a9529-660c-4b7e-a281-d9dda634f056" method="POST" enctype="multipart/form-data">
            <v-row class="mt-10">
              <v-col cols="12" sm="6">
                <v-text-field
                  type="text"
                  label="Name"
                  persistent-hint
                  variant="outlined"
                  name="name"
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="6">
                <v-text-field
                  type="email"
                  label="Email"
                  persistent-hint
                  variant="outlined"
                  name="email"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-textarea
              label="Message"
              persistent-hint
              variant="outlined"
              name="message"
            ></v-textarea>
            <div class="button-container">
              <v-btn color="#2288f5" class="mr-2" type="submit">Submit Now</v-btn>
              <v-btn color="red" dark @click="goBack">Go back</v-btn>
          </div> 
          
  <div class="lowered">
    <div id="map" style="width: 100%; height: 400px; position: relative;"></div>

  </div>

          </form>
         
        </v-col>
      </v-row>
    </v-row>
    </v-col>
</v-container>
<FooterView />
</v-app>

  </template>
  
  <script>
  import NavBar from "../components/NavBar2.vue";
  import FooterView from "../components/FooterView.vue";
  import L from 'leaflet';
  import markerIcon from "@/assets/marker.png";
  import "leaflet/dist/images/marker-icon.png";
  import "leaflet/dist/images/marker-shadow.png";
  export default {
    name: "ContactView",
    components: {
    NavBar,
    FooterView
  },

  mounted() {
    this.initMap();
  },

    methods: {
        initMap() {
            const map = L.map('map', { preferCanvas: true }).setView([54.3776591, 18.6073165], 13);


      L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: 'Map data © <a href="https://openstreetmap.org">OpenStreetMap</a> contributors',
        maxZoom: 18,
      }).addTo(map);
// eslint-disable-next-line no-unused-vars
const marker = L.marker([54.3776591, 18.6073165], { icon: L.icon({ iconUrl: markerIcon }) }).addTo(map);
marker.setIcon(L.icon({
  iconUrl: require('@/assets/map-marker.png'),
  iconSize: [32, 32], 
}));
      map.invalidateSize();
    
  },

      goBack() {
        this.$router.go(-1); // Go back to the previous page
        location.reload;
      }
      }
  };
  </script>

<style>
@import '~leaflet/dist/leaflet.css';

.lowered {
  margin-top: 25px;
}
</style>