<template>
  <div>
    <!-- Header without a border -->
    <ion-header class="ion-no-border">
      <ion-toolbar>
        <ion-title>Covid-19 Tracker</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-tabs>
      <ion-tab tab="tab-map" component="page-map">
        <div style="width:100%; height:70%" id="mapContainer"></div>
        <ion-card color="success">
          <ion-card-header color="primary">
            <ion-card-title>Rating :27.34 ~ Mild Risk</ion-card-title>
          </ion-card-header>

          <ion-card-content>
            <h2>
              Accra is a populated area, kindly use your nose mask and observe social
              distancing as much as possible
            </h2>
          </ion-card-content>
        </ion-card>
      </ion-tab>

      <ion-tab tab="tab-about" component="page-about">
        <h1>dfddf</h1>
      </ion-tab>

      <ion-tab-bar slot="bottom">
        <ion-tab-button tab="tab-map">
          <ion-icon name="navigate-circle-outline"></ion-icon>
          <ion-label>Scan Area</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="tab-about">
          <ion-icon name="chatbubble-ellipses-outline"></ion-icon>
          <ion-label>Ask me about covid-19</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </div>
</template>

        <script src="https://js.api.here.com/v3/3.1/mapsjs-core.js" type="text/javascript" charset="utf-8"></script>
        <script src="https://js.api.here.com/v3/3.1/mapsjs-service.js" type="text/javascript" charset="utf-8"></script>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      platform: "",
      defaultLayers: "",
      map: ""
    };
  },
  mounted() {
    // Obtain the default map types from the platform object
    this.platform = new H.service.Platform({
      apikey: "Dc7kwkfyYH76w0bnio9N3s1DlFWTZC9npqqig40UP4Y"
    });

    // Obtain the default map types from the platform object:
    this.defaultLayers = this.platform.createDefaultLayers();

    // Instantiate (and display) a map object:
    this.map = new H.Map(
      document.getElementById("mapContainer"),
      this.defaultLayers.vector.normal.map,
      {
        zoom: 10,
        center: { lng: 8.5342, lat: 50.1622 }
      }
    );

    H.ui.UI.createDefault(this.map, this.defaultLayers);
  },
  methods: {}
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

canvas {
  width: 100%;
  height: 100%;
}
</style>
