<template>
  <v-container>
    <v-row>
      <v-col sm="3" md="4" class="img-contact">
        <v-avatar color="grey" size="300">
          <v-img src="@/assets/images/foto-carnet.png"> </v-img>
        </v-avatar>
      </v-col>
      <v-col sm="8" md="8" class="text-contact">
        <p>Estas son algunas de mis redes personales</p>
        <div class="btns-contact d-flex flex-column">
          <v-btn
            class="my-3"
            dark
            link
            href="https://www.linkedin.com/in/fabian-david-guevara-pinilla-417089182/"
          >
            Fabian David Guevara Pinilla
            <v-icon style="margin-inline: 0.5rem">mdi-linkedin</v-icon>
          </v-btn>
          <v-btn class="my-3" dark link href="https://twitter.com/davidpinilla12">
            @davidpinilla12
            <v-icon style="margin-inline: 0.5rem">mdi-twitter</v-icon>
          </v-btn>
          <v-btn
            class="my-3"
            dark
            link
            href="https://www.instagram.com/fabiandavidguevara/"
          >
            @fabiandavidguevara
            <v-icon style="margin-inline: 0.5rem">mdi-instagram</v-icon>
          </v-btn>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Test",
  created() {},
  data() {
    return {};
  },
  props: {},
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "@/assets/styles/global.scss";
.img-contact {
  display: flex;
  justify-content: flex-end;
}
.text-contact {
  // background-color: $color-gray;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-content: center;
  padding: 2rem 0;
  & p {
    color: $color-white;
    font-size: large;
    text-align: center;
  }
  & .btns-contact {
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
