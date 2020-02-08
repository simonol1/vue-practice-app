<template>
  <div class="race-list__container">
    <!-- <ul class="race-list">
      <li class="race-list__item" v-for="(race,index) in races" :key="index"> -->
        <HorseRaces></HorseRaces>
      <!-- </li> -->
        <HarnessRaces></HarnessRaces>
        <GreyhoundRaces></GreyhoundRaces>
    <!-- </ul> -->
  </div>
</template>

<script>
import axios from 'axios';

import HorseRaces from './HorseRaces.vue'
import HarnessRaces from './HarnessRaces.vue'
import GreyhoundRaces from './GreyhoundRaces.vue'


export default {
  name: 'RaceList',

  components: {
    HarnessRaces,
    HorseRaces,
    GreyhoundRaces
  },

  data () {
    return {
      races: null
    }
  },

  mounted () {
    axios
      .get('https://api.neds.com.au/rest/v1/racing/?method=nextraces&count=10')
      .then(res => {
        this.races = res.data;
        console.log(res.data.race_summaries);
      }).catch(error => {
        console.log(error);
      })
  },
}
</script>

<style lang="scss">

ul li {
  margin: 0;
  padding: 0;
  list-style-type: none;
}

</style>
