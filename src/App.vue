<template>
  <div id="app">
    <div class="page-wrapper">
      <RaceFilter></RaceFilter>
      <RaceList></RaceList>
    </div>
  </div>
</template>

<script>
import RaceFilter from './components/RaceFilter.vue'
import RaceList from './components/RaceList.vue'

export default {
  name: 'App',
  components: {
    RaceFilter,
    RaceList
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  .page-wrapper {
    max-width: 1280px;
    padding: 30px;

    ul, li {
      margin: 0;
      padding: 0;
      list-style-type: none;
    }
    .race-filter {

      &__container {
        display: flex;
        margin-left: auto;
      }

      &__heading {
        display: flex;
        align-items: center;
        max-width: 80px;
        margin: 0;
        padding: 5px 0;
        border: 1px solid #d6d6d6;
        background-color: #303030;
        color: #fff;
        border-bottom: none;
        text-align: center;
      }

    }

    .race-list {
      border: 1px solid #d6d6d6;
      border-bottom: none;
      max-width: 320px;

      &__item {
        position: relative;
        -moz-box-shadow:    inset 0 0 10px #c9c9c9;
        -webkit-box-shadow: inset 0 0 10px #c9c9c9;
        box-shadow:         inset 0 0 10px #c9c9c9;
        cursor: pointer;
        padding: 5px 5px 5px 30px;
        border-bottom: 1px solid #d6d6d6;
        text-align: left;
        background-repeat: no-repeat;
        background-size: 20px;
        background-position: 5px;


        &:hover {
          background-color: #d6d6d6;
        }

        .item {
          &__race-number {
            display: inline-block;
            font-weight: 600;
            padding: 0 5px;
            width: 45px;
          }
          &__meeting-name {
            padding: 0 5px;
          }
          &__start-time {
            position: absolute;
            right: 0;
            top: 5px;
            padding: 0 5px;
          }
        }
      }
    }
  }
}


.btn {
  border: 1px solid #d6d6d6;
  border-bottom: 0;
  cursor: pointer;
  height: 60px;
  width: 80px;
  background-size: 40px;
  background-repeat: no-repeat;
  background-position: center;

  &:focus {
    outline: none;
  }

  &:nth-child(2) {
    border-left: none;
    border-right: none;
  }
  &:nth-child(3) {
    border-right: none;
  }

  &.active {
    background-color: #ff7800;
  }

  &:hover {
    background-color: #ff7800;
    opacity: 0.8;
  }
}

.horse {
  background-image: url('./assets/horse-racing.svg');
}

.harness {
  background-image: url('./assets/harness.svg');
}

.greyhound {
  background-image: url('./assets/greyhound.svg');
}

</style>
