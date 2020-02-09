<template>
  <button :class="[{active: isActive}, category]" class="btn"  @click="toggleBtn(category)"></button>
</template>

<script>


export default {
  name: 'FilterBtn',
  props: ['category'],
  data () {
    return {
      isActive: true,
    }
  },

  methods: {
    toggleBtn(category) {
      this.isActive = !this.isActive;

      console.log(category);
    }
  },
}
</script>
