<template>
  <v-app id="inspire">
    <!-- <v-card class="overflow-hidden"> -->
    <Navbar title="My portfolio"></Navbar>

    <v-sheet class="contenedor_principal" max-height="5000">
      <v-container style="height: 100%; padding-top: 100px; margin-bottom: 100px">
        <router-view> </router-view>
      </v-container>
    </v-sheet>
    <Footer></Footer>
    <!-- </v-card> -->
  </v-app>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";
export default {
  data: () => ({
    links: ["Dashboard", "Messages", "Profile", "Updates"],
  }),
  components: { Navbar, Footer },
};
</script>

<style lang="scss" scoped>
@import "@/assets/styles/global.scss";
.contenedor_principal {
  background-color: $color-black;
}
</style>
