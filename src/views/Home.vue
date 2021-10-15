<template>
  <v-container>
    <v-row class="div-presentacion">
      <v-col class="descripcion_titulos">
        <h1 class="descripcion_titulos">Hello, I am</h1>
        <h1 class="descripcion_titulos decripcion-animated">
          {{ descripcionTitles }}
        </h1>
      </v-col>
      <v-col>
        <v-img
          height="320"
          cover
          src="https://c.tenor.com/j3cVEPj4bzkAAAAC/cat-typing.gif"
        >
        </v-img>
      </v-col>
    </v-row>

    <v-row class="about-container">
      <v-col
        cols="6"
        sm="6"
        md="3"
        style="border-width: 0 3px 0 0; border-color: white; border-style: solid"
      >
        <h1 class="text-right titulos-home">About me</h1>
      </v-col>
      <v-col cols="6" sm="6" md="9">
        <p class="ps-5 texto-about-home text-justify">
          Soy un joven colombiano, que quiere desarrollar tecnología en el país,
          desarrollar proyectos, aunque me veo limitado en ciertos conocimientos, siento
          que mi mayor debilidad es no mantener la constancia en el desarrollo para que
          estos desarrollos de hobby lleguen a ver la luz. Me gusta ser curioso y
          cuestionarme varias cosas, también siento que una amenaza para el desarrollo
          total de mis habilidades o el sentimiento de querer seguir esforzándome es la
          sensación de que nada importa y lo que consideramos desarrollo es algo impuesto
          y cohíbe el desarrollo del ser. Por lo tanto, el sentimiento de plenitud es algo
          que busco constantemente.
        </p>
      </v-col>
    </v-row>
    <v-row class="study-container">
      <v-col cols="6" sm="6" md="9">
        <div class="TimeLine">
          <timeline-item
            v-for="(item, idx) in eventos"
            :key="idx"
            :year="item.year"
            :TitleEvent="item.titulo"
            :TextEvent="item.texto"
          ></timeline-item>
        </div>
      </v-col>
      <v-col
        cols="6"
        sm="6"
        md="3"
        style="border-width: 0 0 0 3px; border-color: white; border-style: solid"
      >
        <h1 class="titulos-home">Estudios</h1>
      </v-col>
    </v-row>
    <v-row> </v-row>
  </v-container>
</template>

<script>
import TimelineItem from "./../components/TimelineItem.vue";

export default {
  name: "Home",
  data() {
    return {
      pos: 0,
      titulos: ["robot", "developer", "engineer"],
      intervalo: undefined,
      eventos: [
        {
          year: 2014,
          titulo: "Graduación secundaria",
          texto: "Bachiller técnico en diseño gráfico de proyectos de construcción",
        },
        {
          year: 2020,
          titulo: "Finalización carrera universitaria",
          texto: "Profesional en Ingeniería electrónica -  Universidad Surcolombiana",
        },
        {
          year: 2021,
          titulo: "Realización técnico en el SENA- En curso",
          texto: "Instalación y mantenimiento de redes inalámbricas",
        },
      ],
    };
  },
  computed: {
    descripcionTitles() {
      return this.titulos[this.pos];
    },
  },
  created() {
    var self = this;
    let lenghtTitles = this.titulos.length;
    console.log(lenghtTitles);
    this.intervalo = setInterval(function () {
      if (self.pos < lenghtTitles - 1) {
        self.pos++;
      } else {
        self.pos = 0;
      }
      console.log(self.pos);
    }, 3000);
  },
  beforeDestroy() {
    clearInterval(this.intervalo);
  },
  components: {
    TimelineItem,
  },
};
</script>
<style lang="scss" scoped>
@import "@/assets/styles/global.scss";
.titulos-home {
  color: $color-titles-2;
}
.texto-about-home {
  color: $color-white;
}
.div-presentacion {
  padding: 2rem 0rem;
}
.descripcion_titulos {
  color: $color-titles-2;
  align-items: flex-start;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.decripcion-animated {
  font-size: 4rem;
  animation: move-bounce 3s ease-in infinite;
  transform-origin: center;
  @keyframes move-bounce {
    from {
      transform: rotateZ(3deg) scale(1.2);
    }
    to {
      transform: rotateZ(-3deg) scale(1.1);
    }
  }
}

.about-container {
  min-height: 300px;
  padding-block: 2rem;
}
.study-container {
  padding-block: 2rem;
  min-height: 400px;
}
</style>
