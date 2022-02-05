<template>
  <v-container>
    <v-row>
      <v-col
        cols="12"
      >
        <v-text-field
          v-model="search"
          solo
          label="Search"
          clearable
        ></v-text-field>
      </v-col>
      <v-col
        cols="6"
        xs="6"
      >
        <CityCard
          temperature="22"
          city="Berlin"
        />
      </v-col>
      <v-col
        cols="6"
        xs="6"
      >
        <CityCard
          temperature="18"
          city="Frankfurt"
        />
      </v-col>
      <v-col
        cols="6"
        xs="6"
      >
        <CityCard
          temperature="12"
          city="Rom"
        />
      </v-col>
      <v-col
        cols="6"
        xs="6"
      >
        <CityCard
          temperature="17"
          city="Paris"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue';
import CityCard from '@/components/home/CityCard.vue';

export default Vue.extend({
  name: 'Home',
  components: {
    CityCard,
  },
  data: () => ({
    search: '',
  }),
});
</script>
