<template>
  <div class="race-list__container">
    <ul class="race-list">
      <li class="race-list__item" v-for="(race,index) in races" :key="index" :class="{'greyhound': race.category_id == category_ids.greyhound, 'horse': race.category_id == category_ids.horse, 'harness': race.category_id == category_ids.harness }">
        <Race :categoryid="race.category_id" :racenumber="race.race_number" :meetingname="race.meeting_name" :starttime="race.advertised_start.seconds"></Race>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

import Race from './Race.vue'

export default {
  name: 'RaceList',

  components: {
    Race
  },

  data() {
    return {
      races: [],
      category_ids: {
        greyhound: '9daef0d7-bf3c-4f50-921d-8e818c60fe61',
        horse: '4a2788f8-e825-4d36-9894-efd4baf1cfae',
        harness: '161d9be2-e909-4326-8c2c-35ed71fb460b'
      }
    }
  },

  mounted() {
    axios
      .get('https://api.neds.com.au/rest/v1/racing/?method=nextraces&count=5')
      .then(res => {
        this.races = res.data.data.race_summaries;
        console.log('data fetched');
      }).catch(err => {
        console.log(err);
      })
  },

  computed: {
    filterByStartTime() {
      console.log('computed')
      return this.races.slice().sort((a, b) => { return b.advertised_start.seconds - a.advertised_start.seconds;});
    }
  },

  watch: {
    races: function() {
        console.log('race data updated');
    }
  }
}
</script>
