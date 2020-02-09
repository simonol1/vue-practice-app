<template>
  <div class="race-list__container">
    <ul class="race-list">
      <li class="race-list__item" :class="{'greyhound': race.category_id == category_ids.greyhound, 'horse': race.category_id == category_ids.horse, 'harness': race.category_id == category_ids.harness }" v-for="(race,index) in races" :key="index">
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
      races: null,
      category_ids: {
        greyhound: '9daef0d7-bf3c-4f50-921d-8e818c60fe61',
        horse: '4a2788f8-e825-4d36-9894-efd4baf1cfae',
        harness: '161d9be2-e909-4326-8c2c-35ed71fb460b'
      }
    }
  },

  mounted () {
    axios
      .get('https://api.neds.com.au/rest/v1/racing/?method=nextraces&count=10')
      .then(res => {
        this.races = res.data.data.race_summaries;

      }).catch(err => {
        console.log(err);
      })
  },

  // computed: {
  //   filterByStartTime() {
  //     const startTime = this.race.advertised_start.seconds;
  //     const sortByTime = startTime.slice(0);

  //     sortByTime.sort(function(a,b) {
  //         return a.startTime - b.startTime;
  //     });
  //     return sortByTime
  //   }
  // }
}
</script>
