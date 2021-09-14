<template>
  <div class="main-layout">
    <header-layout :user="user" />
    <router-view />
    <footer-layout />
  </div>
</template>
<style lang="scss">
</style>

<script>
import HeaderLayout from "./components/HeaderLayout.vue";
import FooterLayout from "./components/FooterLayoy.vue";

export default {
  components: {
    HeaderLayout,
    FooterLayout,
  },
  data() {
    return {
      user: {
        name: "Lita4421",
        img: "/assets/images/avatar.png",
      },
    };
  },
  created() {
    this.user = null;
  },
};
</script>

<style lang="scss">
@import "./assets/style/style.scss";
</style>