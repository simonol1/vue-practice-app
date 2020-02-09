<template>
  <span>
    <span v-if="racenumber" class="item__race-number">R{{ racenumber }}</span>
    <span v-if="meetingname" class="item__meeting-name">{{ meetingname }}</span>
    <span v-if="starttime" class="item__start-time">{{ starttime | niceTime}}m</span>
  </span>
</template>

<script>
export default {
  name: 'Race',
  props: [ 'categoryid', 'racenumber', 'meetingname', 'starttime'],

  filters: {
    niceTime(value) {
      let currentTime = Math.round(+new Date()/1000);
      let minsToJump = Math.round((value - currentTime)/60);

      return minsToJump;
    }
  }
}

</script>
