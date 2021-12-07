<template>
  <v-container>
    <h3>Weather App</h3>
    <v-card class="card">
      <v-card-text>
        <p v-if="city !== ''">Weather : {{ weather }}</p>
      </v-card-text>
    </v-card>

    <v-form @submit.prevent="getWeather">
      <v-text-field label="Enter The City Name" v-model="city"></v-text-field>
    </v-form>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      city: "",
      weather: {},
    };
  },
  created() {
    this.getWeather();
  },
  methods: {
    getWeather() {
      this.$axios
        .$get(
          `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=d39ba1887f5afda75432861a1bff53d7`
        )
        .then((res) => (this.weather = res));
    },
  },
};
</script>
<style>
h3 {
  text-align: center;
}
.card {
  margin-top: 10px;
  background-color: yellow !important;
}
</style>
