<template>
  <v-app-bar color="#050505" absolute dark>
    <!-- <v-app-bar-nav-icon></v-app-bar-nav-icon> -->

    <v-app-bar-title style="width: 100%; font-size: 24px">{{ title }}</v-app-bar-title>

    <v-spacer></v-spacer>

    <!-- <v-btn icon>
      <v-icon>mdi-magnify</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>mdi-heart</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>mdi-dots-vertical</v-icon>
    </v-btn> -->

    <template v-slot:extension>
      <v-tabs centered grow style="padding-inline: 2rem">
        <v-tab @click="redirectTo(link)" v-for="link in links" :key="link">
          {{ link }}
        </v-tab>
      </v-tabs>
    </template>
  </v-app-bar>
</template>
<script>
export default {
  props: ["title"],
  data() {
    return {
      links: ["Inicio", "Proyectos", "Contacto"],
    };
  },
  methods: {
    redirectTo(link) {
      if (this.$route.name != link) {
        this.$router.push(link);
      }
    },
  },
};
</script>
