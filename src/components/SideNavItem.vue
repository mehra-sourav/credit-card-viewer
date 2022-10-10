<template>
  <q-item
    clickable
    class="q-pl-sm"
  >
    <q-item-section
      side
    >
      <q-icon size="sm">
        <img :src="imgPath" :alt="icon"/>
      </q-icon>
    </q-item-section>

    <q-item-section>
      <q-item-label
       :class="{
        'sidenav__item--active': active,
        'text-weight-bold' : active
       }"
      >
        {{ title }}
      </q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  name: 'SideNavItem',
  props: {
    title: {
      type: String,
      required: true
    },
    icon: {
      type: String,
      default: ''
    },
    active: {
      type: Boolean,
      default: false
    }
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
