<template>
  <div class="city-detail-wrapper">
    <v-row class=" pr-4">
      <v-col
        class="d-flex justify-center flex-column align-start pa-8"
        cols="6"
      >
        <p>{{city}}</p>
        <p class="temperature">{{temperature}}°C</p>
        <v-chip
          color="#2F2D54"
        >
          sonnig
        </v-chip>
      </v-col>
      <v-col
        cols="6"
      >
        <v-img
          contain
          max-width="250"
          max-height="250"
          src="@/assets/weather/sun-large.png"
        />
      </v-col>
    </v-row>
    <v-row class="mt-8 pr-4 text-center info-row">
      <v-col
        cols="4"
      >
        <v-img max-height="20" max-width="20" src="@/assets/weather/wet.png" />
        14%
      </v-col>
      <v-col
        cols="4"
      >
        <v-img max-height="20" max-width="20" src="@/assets/weather/pressure.png" />
        1.025 hPa
      </v-col>
      <v-col
        cols="4"
      >
        <v-img max-height="20" max-width="20" src="@/assets/weather/wind.png" />
        19 km/h
      </v-col>
    </v-row>
    <v-row class="mt-8 pr-4">
      <v-col cols="12" class="pl-8">
        <p>Today</p>
      </v-col>
      <v-col cols="12">
        <div class="weather-time-container">
          <WeatherTime
            v-for="n in 12"
            :key="n"
            :time="n + 10"
          />
        </div>
      </v-col>

    </v-row>
    <v-row class="mt-4 pl-8 pr-4">
      <v-col cols="12">
        <WeatherDays
          day="Tuesday"
          :temperature="20"
        />
      </v-col>
      <v-col cols="12">
        <WeatherDays
          day="Wednesday"
          :temperature="16"
        />
      </v-col>
      <v-col cols="12">
        <WeatherDays
          day="Thursday"
          :temperature="18"
        />
      </v-col>
    </v-row>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import WeatherTime from '@/components/city/WeatherTime.vue';
import WeatherDays from '@/components/city/WeatherDays.vue';

export default Vue.extend({
  name: 'CityDetail',
  components: {
    WeatherTime,
    WeatherDays,
  },
  props: {
    city: {
      type: String,
      required: true,
    },
    temperature: {
      type: String,
      required: true,
    },
  },
  data: () => ({
    //
  }),
  methods: {
    //
  },
});
</script>

<style lang="scss" scoped>
.city-detail-wrapper {
  margin-top: 8%;
  p {
    margin: 0;
  }
  .temperature {
    font-size: 70px;
  }
  .info-row {
    .col {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.25rem;
    }
  }
  .weather-time-container {
    width: 100%;
    display: flex;
    overflow-x: auto;
  }
}
</style>
