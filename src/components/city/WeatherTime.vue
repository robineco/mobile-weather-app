<template>
  <div class="weather-time-wrapper">
    <p>{{getTime}}</p>
    <v-img
      max-width="30"
      max-height="30"
      src="@/assets/weather/sun.png"
    />
    <p>{{getTemperature}}</p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'WeatherTime',
  props: {
    time: {
      type: Number,
      required: true,
    },
  },
  data: () => ({
    //
  }),
  computed: {
    getTime() {
      return `${this.time}:00`;
    },
    getTemperature() {
      const temp = 30 - this.time;
      return `${temp}°C`;
    },
  },
  methods: {
    //
  },
});
</script>

<style lang="scss" scoped>
.weather-time-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 4.5rem;
  flex-shrink: 0;
  p {
    margin: 0;
  }
  > .v-image {
    margin: 0.5rem 0;
  }
}
</style>
