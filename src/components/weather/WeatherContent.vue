<template>
  <div class="weather-wrapper">
    <ContentHeader />
    <CitySelector @selectCity="selectCity" />
    <WeatherList :weatherList="weatherList" />
  </div>
</template>

<script>
import ContentHeader from "./ContentHeader.vue";
import CitySelector from "./CitySelector.vue";
import WeatherList from "./WeatherList.vue";
import weatherMixin from "@/mixins/weatherMixin";
export default {
  name: "weath-contents",
  components: {
    ContentHeader,
    CitySelector,
    WeatherList,
  },
  data() {
    return {
      weatherList: [],
    };
  },
  mixins: [weatherMixin],
  methods: {
    async selectCity(city) {
      if (city.selected) {
        const weather = await this.getWeatherInfo(city);
        this.weatherList.push(weather);
      } else {
        const index = this.weatherList.findIndex(
          (weather) => weather.code === city.code
        );
        this.weatherList.splice(index, 1);
      }
    },
  },
};
</script>

<style></style>
