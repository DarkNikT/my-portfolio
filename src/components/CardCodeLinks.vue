<template>
  <v-card class="mx-auto" max-width="400" height="520" dark>
    <v-img class="white--text align-end" :height="heightImage" :src="propImage">
      <v-card-title class="titulo_card">{{ titleCard }}</v-card-title>
    </v-img>

    <v-card-subtitle class="pb-0">{{ subtitulo_card }}</v-card-subtitle>

    <v-card-text class="text--light">
      <div>{{ texto_card }}</div>
    </v-card-text>

    <v-card-actions class="d-flex justify-space-around mb-6">
      <!-- <v-btn color="orange" text> Share </v-btn> -->

      <v-btn color="blue" dark :href="link_git" link large>
        <v-icon large left class="px-2"> mdi-github </v-icon> Explore
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: "Test",
  created() {},
  data() {
    return {};
  },
  props: [
    "propImage",
    "heightImage",
    "titleCard",
    "subtitulo_card",
    "texto_card",
    "link_git",
  ],
  methods: {},
};
</script>

<style lang="scss" scoped>
.titulo_card {
  color: rgb(4, 6, 24);
  background-image: linear-gradient(to top, rgba(255, 255, 255, 0.4), transparent);
}
</style>
