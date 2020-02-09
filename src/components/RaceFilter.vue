<template>
  <div class="race-filter__container">
    <h4 class="race-filter__heading">Next 5 Races</h4>
    <FilterBtn :category="'horse'"></FilterBtn>
    <FilterBtn :category="'harness'"></FilterBtn>
    <FilterBtn :category="'greyhound'"></FilterBtn>
  </div>
</template>

<script>
import FilterBtn from './FilterBtn.vue'


export default {
  name: 'RaceFilter',

  components: {
    FilterBtn
  }

}
</script>

