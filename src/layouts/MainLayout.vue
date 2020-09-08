<template>
  <div class="app-main-layout">
    <Navbar @toggle-sidebar="ToggleSidebar" />
    <SideBar :isSideBarOpened="isSideBarOpened" />
    <main class="app-content" :class="{'full': !isSideBarOpened}">
      <div class="app-page">
        <router-view />
      </div>
    </main>

    <div class="fixed-action-btn">
      <router-link class="btn-floating btn-large blue" to="/record">
        <i class="large material-icons">add</i>
      </router-link>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar";
import SideBar from "@/components/SideBar";
export default {
  data: () => ({
    isSideBarOpened: true,
  }),
  methods: {
    ToggleSidebar() {
      this.isSideBarOpened = !this.isSideBarOpened;
    },
  },
  components: {
    Navbar,
    SideBar,
  },
};
</script>

<style>
</style>