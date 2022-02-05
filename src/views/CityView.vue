<template>
  <v-container>
    <CityDetail
      temperature="22"
      city="Berlin"
    />
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue';
import CityDetail from '@/components/city/CityDetail.vue';

export default Vue.extend({
  name: 'CityView',
  components: {
    CityDetail,
  },
  props: {
    //
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

</style>
