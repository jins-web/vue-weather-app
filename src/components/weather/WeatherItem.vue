<template>
  <li class="weather-item">
    <h3>{{ weather.label }}</h3>
    <p class="temperature">{{ weather.temperature }}&deg;</p>
    <p class="info">
      <img :src="weather.icon" alt="any" />
      <span>습도 {{ weather.humidity }}</span>
      <span>바람 {{ weather.wind }}m/s</span>
    </p>
  </li>
</template>

<script>
export default {
  name: "weatherItem",
  props: {
    weather: {
      type: Object,
      default() {
        return {
          label: "서울",
          code: "Seoul",
          temperature: 20,
          humidity: 15,
          wind: 1.5,
        };
      },
    },
  },
};
</script>

<style scoped>
.weather-item {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.weather-item h3 {
  font-size: 14px;
  color: #333;
}
.temperature {
  font-size: 35px;
}
.info {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 12px;
}
.info * {
  margin-right: 0.4em;
}
</style>
