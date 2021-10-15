<template>
  <div class="projects-page">
    <v-row class="d-flex justify-center">
      <h1 class="titulos_page-projectos">Desarrollo de software</h1>
    </v-row>
    <v-divider class="my-3"></v-divider>
    <v-row>
      <v-col class="d-flex">
        <card-code-links
          :heightImage="350"
          :propImage="require('@/assets/images/card_deploy_java.png')"
          titleCard="Integración SQLite-JAVA"
          subtitulo_card="Proyecto realizado en Mision TIC 2022"
          texto_card="Programa en JAVA con interfaz gráfica que permite realizar consultas a una base de datos local SQLite"
          link_git="https://github.com/DarkNikT/Reto5-Grupo2-Ciclo2-MisionTIC2022"
        ></card-code-links>
        <card-code-links
          :heightImage="350"
          :propImage="require('@/assets/images/card_deploy_vue.png')"
          titleCard="Aplicación MEVN"
          subtitulo_card="Proyecto realizado en Mision TIC 2022 ciclo 3"
          texto_card="Aplicación web que integra MongoDb, Express, Vue JS y Node JS"
          link_git="https://github.com/FabianGuevaraPinilla/appweb-grupo2-e4-ciclo3-misiontic-UTP"
        ></card-code-links>
      </v-col>
    </v-row>
    <v-divider class="my-3"></v-divider>
    <v-row class="d-flex justify-center mt-4">
      <h1 class="titulos_page-projectos">Dibujos CSS</h1>
      <project-list :codepens="codepen.css" :username="codepen.username"></project-list>
    </v-row>
    <v-row class="d-flex justify-center">
      <v-btn color="white" link href="https://codepen.io/darknikt">ver más</v-btn>
    </v-row>
  </div>
</template>

<script>
import ProjectList from "./../components/ProjectList.vue";
import CardCodeLinks from "./../components/CardCodeLinks.vue";
export default {
  name: "Test",
  mounted() {},
  data() {
    return {
      codepen: {
        username: "DarkNikT",
        css: [
          {
            id: 1,
            slug_hash: "XWppqJZ",
            title: "Logo Spiderman",

            rows: 2,
            cols: 2,
          },
          {
            id: 2,
            slug_hash: "yLgjwYd",
            title: "Dark Vader",
            rows: 1,
            cols: 1,
          },
          {
            id: 3,
            slug_hash: "JjbyvLo",
            title: "Yoda baby",
            rows: 1,
            cols: 1,
          },
          {
            id: 4,
            slug_hash: "ExZWJjb",
            title: "Casco Ironman",
            rows: 1,
            cols: 2,
          },
          {
            id: 5,
            slug_hash: "NWdVGbe",
            title: "Picoro",
            rows: 1,
            cols: 1,
          },

          {
            id: 6,
            slug_hash: "MWbZwOL",
            title: "Kermit",
            rows: 1,
            cols: 1,
          },
          {
            id: 7,
            slug_hash: "eYgzXJe",
            title: "Logo Wonderwoman",
            rows: 1,
            cols: 1,
          },

          {
            id: 8,
            slug_hash: "RwoZKpm",
            title: "Calabaza",
            rows: 1,
            cols: 1,
          },
          {
            id: 9,
            slug_hash: "eYvJjVz",
            title: "Picachu",
            rows: 2,
            cols: 2,
          },
          {
            id: 10,
            slug_hash: "zYoRMvO",
            title: "Ventana",
            rows: 1,
            cols: 1,
          },
          {
            id: 11,
            slug_hash: "yLVryra",
            title: "Guitarra",
            rows: 1,
            cols: 1,
          },
        ],
      },
    };
  },
  props: {},
  methods: {},
  components: { ProjectList, CardCodeLinks },
};
</script>

<style lang="scss" scoped>
@import "@/assets/styles/global.scss";
.titulos_page-projectos {
  color: $color-titles-2;
  text-align: center;
}
.projects-page {
  padding: 2rem 0;
}
</style>
