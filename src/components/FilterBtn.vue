<template>
  <button :class="[{active: isActive}, btncategory]" class="btn"  @click="toggleBtn(btncategory)"></button>
</template>

<script>


export default {
  name: 'FilterBtn',
  props: ['btncategory'],
  data () {
    return {
      isActive: true,
    }
  },

  methods: {
    toggleBtn(btncategory) {
      this.isActive = !this.isActive;



      console.log(btncategory);
    }
  },
}
</script>
