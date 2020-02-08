<template>
  <div class="race-filter__container">
    <button :class="{active: isActive}" class="btn horse" @click="toggleFilter"></button>
    <button :class="{active: isActive}" class="btn harness" @click="toggleFilter"></button>
    <button :class="{active: isActive}" class="btn greyhound" @click="toggleFilter"></button>
  </div>
</template>

<script>
export default {
  name: 'RaceFilter',

  data() {
    return {
      isActive: true,
    }
  },

  methods: {
    toggleFilter() {
      var self = this;
      self.isActive = !self.isActive;
    }
  }
}
</script>

<style lang="scss">

.btn {
  cursor: pointer;
  height: 60px;
  width: 80px;
  background-size: 40px;
  background-repeat: no-repeat;
  background-position: center;

  &:nth-child(2) {
    border-left: none;
    border-right: none;
  }

  &:hover {
    background-color: #ff7800;
  }

  &.horse {
    background-image: url('../assets/horse-racing.svg');
  }

  &.harness {
    background-image: url('../assets/harness.svg');
  }

  &.greyhound {
    background-image: url('../assets/greyhound.svg');
  }

}
</style>
