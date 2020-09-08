<template>
  <ul class="sidenav app-sidenav" :class="{open: isSideBarOpened}">
    <router-link
      v-for="link in links"
      :key="link.url"
      :to="link.url"
      active-class="active"
      tag="li"
      exact
    >
      <a href="#" class="waves-effect waves-orange pointer">{{link.title}}</a>
    </router-link>
  </ul>
</template>

<script>
export default {
  data: () => ({
    links: [
      { title: "Счет", url: "/" },
      { title: "История", url: "/history" },
      { title: "Планирование", url: "/planning" },
      { title: "Новая запись", url: "/record" },
      { title: "Категории", url: "/categories" },
    ],
  }),
  props: {
    isSideBarOpened: {
      type: Boolean,
      required: true
    }
  },
};
</script>

<style>
</style>