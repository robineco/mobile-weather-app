<template>
  <div
    class="city-card-wrapper"
    @click="$router.push('/city')"
  >
    <v-container>
      <v-row
        class="text-center"
      >
        <v-col
          class="d-flex justify-center flex-column align-start"
          cols="6"
        >
          <p class="temperature">{{temperature}}°C</p>
          <p>{{city}}</p>
        </v-col>
        <v-col
          class="d-flex justify-center"
          cols="6"
        >
          <v-img
            contain
            max-height="40"
            max-width="40"
            src="@/assets/weather/sun.png"
          />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'CityCard',
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
.city-card-wrapper {
  background-color: #192731;
  border-radius: 16px;
  p {
    margin-bottom: 0.5rem;
  }
  .temperature {
    font-size: 28px;
  }
}
</style>
