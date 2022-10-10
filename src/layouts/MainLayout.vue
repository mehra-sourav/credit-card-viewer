<template>
  <q-layout view="lHh Lpr lFf">
    <q-drawer
      show-if-above
      class="sidenav"
    >
      <q-item-label
       header
       class="q-ml-md white--text"
      >
        <q-img class="q-ml-sm" :src="aspireIconPath" width="50%" />
        <p class="sidenav__desc-text">
          Trusted way of banking for 3,000+ SMEs and startups in Singapore
        </p>
        <SideNavItem
          v-for="item in sideNavItems"
          :key="item.title"
          :active="item.active"
          v-bind="item"
          class="q-my-xl"
        />
      </q-item-label>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import SideNavItem from 'components/SideNavItem.vue';

export default {
  name: 'mainLayout',

  components: {
    SideNavItem
  },

  data() {
    return {
      leftDrawerOpen: false,
      sideNavItems: [
        {
          title: 'Home',
          icon: 'home',
          active: false
        },
        {
          title: 'Cards',
          icon: 'card',
          active: true
        },
        {
          title: 'Payments',
          icon: 'payment',
          active: false
        },
        {
          title: 'Credit',
          icon: 'credit',
          active: false
        },
        {
          title: 'Settings',
          icon: 'settings',
          active: false
        },
      ],
      aspireIconPath: require("../assets/sidenav/aspire-icon.svg")
    }
  },

  methods: {
  }
}
</script>

<style lang="scss">
  @import "../css/mainLayout.scss";
</style>
