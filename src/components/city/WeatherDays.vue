<template>
  <div class="weather-days-wrapper">
    <v-row no-gutters>
      <v-col cols="6">
        <p>{{day}}</p>
      </v-col>
      <v-col cols="2">
        <v-img max-width="30" max-height="30" src="@/assets/weather/cloudy.png" />
      </v-col>
      <v-col cols="4" class="d-flex justify-end">
        <p>{{getTemperature}}</p>
      </v-col>
    </v-row>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'WeatherDays',
  props: {
    day: {
      type: String,
      required: true,
    },
    temperature: {
      type: Number,
      required: true,
    },
  },
  data: () => ({
    //
  }),
  computed: {
    getTemperature() {
      const night = this.temperature - 5;
      return `${this.temperature}°C | ${night}°C`;
    },
  },
});
</script>

<style lang="scss" scoped>
.weather-days-wrapper {
  p {
    margin: 0;
  }
}
</style>
