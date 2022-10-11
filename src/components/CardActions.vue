<template>
    In Progress (Card buttons)
</template>
<script>
export default {
  name: 'CardActions',
  props: {
    activeCardIdx: {
      type: Number,
      required: true
    },
    cardsList: {
      type: Array,
      default: []
    },
  },
  computed: {
    imgPath() {
      return require(`../assets/sidenav/${this.icon}.svg`);
    }
  }
}
</script>
<style>

.sidenav__item--active {
  color: var(--green);
}

</style>