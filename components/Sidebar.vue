<template>
  <div class="sidebar__content flex-col">
    <img src="bfi.png" alt="" />
    <div class="logo__container">
      <div class="sidebar__toggle" @click="toggleSidebar">
        <v-icon>mdi-menu</v-icon>
        <div v-if="sidebarState" class="logo">
          <h1>DMS</h1>
        </div>
      </div>
      <div v-if="sidebarState" class="app-title">
        <p>DEVICE MANAGEMENT</p>
        <p>SYSTEM</p>
      </div>
    </div>
    <div class="nav__container">
      <router-link
        v-for="(item, i) in navItems"
        :key="i"
        :to="item.to"
        tag="li"
        class="nav__item"
      >
        <span class="nav__icon mr-5">
          <v-icon>{{ item.icon }}</v-icon>
        </span>
        <span v-if="sidebarState" class="nav__title">
          {{ item.title }}
        </span>
      </router-link>
    </div>
    <div class="user__corner">
      <v-icon>mdi-cog-outline</v-icon>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      sidebarState: true,
      navItems: [
        {
          icon: 'mdi-account-cowboy-hat-outline',
          title: 'Admin',
          to: '/inspire'
        },
        {
          icon: 'mdi-apps',
          title: 'Dashboard',
          to: '/inspire'
        },
        {
          icon: 'mdi-account-multiple-outline',
          title: 'Users',
          to: '/Users'
        },
        {
          icon: 'mdi-devices',
          title: 'Devices',
          to: '/Devices'
        }
      ]
    }
  },
  methods: {
    toggleSidebar() {
      // console.log('click')
      this.sidebarState = !this.sidebarState
    }
  }
}
</script>
<style></style>
