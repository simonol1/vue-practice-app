<template>
  <span>
    <span v-if="racenumber" class="item__race-number">R{{ racenumber }}</span>
    <span v-if="meetingname" class="item__meeting-name">{{ meetingname }}</span>
    <span v-if="starttime" class="item__start-time">{{ starttime | niceTime }}</span>
  </span>
</template>

<script>
export default {
  name: 'Race',
  props: [ 'categoryid', 'racenumber', 'meetingname', 'starttime'],

  data() {
    return {
      isActive: true,
    }
  },

  filters: {
    niceTime(value) {
      const currTime = Math.round(new Date()/1000);
      const secsToJump = value - currTime;

      if (secsToJump > 60) {
        const minsToJump = Math.round(secsToJump / 60);
        return minsToJump + 'm';
      } else {
        return secsToJump + 's';
      }
    },

  }
}

</script>
