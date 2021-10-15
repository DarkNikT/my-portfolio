<template>
  <v-footer dark class="footer_page" padless>
    <v-card flat tile class="lighten-1 white--text text-center">
      <v-card-text>
        <!-- <v-btn v-for="icon in icons" :key="icon" class="mx-4 white--text" icon>
          <v-icon size="24px">
            {{ icon }}
          </v-icon>
        </v-btn> -->
      </v-card-text>

      <v-card-text class="white--text pt-0">
        “La vida es y siempre será una ecuación sin solución, pero contiene algunos
        factores conocidos. Podríamos decir, en definitiva, que es un movimiento, incluso
        aunque no entendamos del todo su naturaleza”. Nikola Tesla
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
  }),
};
</script>

<style lang="scss" scoped>
@import "@/assets/styles/global.scss";
.footer_page {
  background-color: $color-dark;
}
</style>
