<template>
  <div :class="`d${propsPen.id} Codepen__item`">
    <v-img
      class="img-fluid"
      :src="imagen || require('@/assets/r2d2.svg')"
      alt=""
      :lazy-src="require('@/assets/r2d2.svg')"
      :min-height="heightImage"
      :aspect-ratio="propsPen.cols / propsPen.rows"
    >
      <template v-slot:placeholder>
        <v-row class="fill-height ma-0" align="center" justify="center">
          <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
        </v-row>
      </template>
    </v-img>

    <!-- {/* <img class="img-fluid" src="`https://codepen.io/${username}/pen/${slug_hash}/image/large.png`" alt="" /> */} -->
    <div :class="`Codepen__item-hover-title-${propsPen.rows}`">
      <h1 class="Codepen__title fs-2 m-0">{{ propsPen.title }}</h1>
      <a class="Codepen__link fs-5 text-decoration-none" :href="urlCodepen">
        Ver código
      </a>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Test",
  created() {},
  data() {
    return {
      imagen: "",
    };
  },
  // props: {id,  slug_hash, title, username, rows, cols},
  props: ["propsPen", "heightImage", "username"],
  computed: {
    urlCodepen() {
      return "https://codepen.io/" + this.username + "/pen/" + this.propsPen.slug_hash;
    },
  },
  mounted() {
    console.log(this.imageCodepen());
    axios
      .get(this.imageCodepen(), {
        responseType: "arraybuffer",
      })
      .then((response) => {
        const base64 = btoa(
          new Uint8Array(response.data).reduce(
            (data, byte) => data + String.fromCharCode(byte),
            ""
          )
        );
        this.imagen = "data:;base64," + base64;
      })
      .catch((e) => {
        // axios
        //   .get(this.urlServer + "/static/images/cross.jpg", {
        //     responseType: "arraybuffer",
        //   })
        //   .then((response) => {
        //     const base64 = btoa(
        //       new Uint8Array(response.data).reduce(
        //         (data, byte) => data + String.fromCharCode(byte),
        //         ""
        //       )
        //     );
        //     this.imagen = "data:;base64," + base64;
        //   });
        console.log("error");
        console.error(e);
      });
  },

  methods: {
    imageCodepen() {
      return (
        "https://assets.codepen.io/3/internal/screenshots/pens/" +
        this.propsPen.slug_hash +
        ".default.png?fit=cover&format=auto&ha=true&height=" +
        this.heightImage *
          (this.propsPen.rows === this.propsPen.cols ? 2 : this.propsPen.rows) +
        "&quality=95&v=2&version=1587738951&width=" +
        this.heightImage *
          (this.propsPen.rows === this.propsPen.cols ? 2 : this.propsPen.cols)
      );
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/styles/global.scss";
@import url("https://fonts.googleapis.com/css2?family=Roboto+Condensed&display=swap");

$color-hover-titulo: rgba(255, 255, 255, 0.412);
$color-hover-text: $color-dark;
.results-type {
  display: none !important;
}
.Codepen__item {
  width: 100%;
  //min-width: 130px;
  position: relative;
}

.d2 {
  grid-area: d2;
}

.d1 {
  grid-area: d1;
}

.d3 {
  grid-area: d3;
}

.d4 {
  grid-area: d4;
}

.d5 {
  grid-area: d5;
}

.d6 {
  grid-area: d6;
}

.d7 {
  grid-area: d7;
}

.d8 {
  grid-area: d8;
}

.d9 {
  grid-area: d9;
}

.d10 {
  grid-area: d10;
}

.d11 {
  grid-area: d11;
}

.d12 {
  grid-area: d12;
}

.d13 {
  grid-area: d13;
}

.d14 {
  grid-area: d14;
}

.d15 {
  grid-area: d15;
}

.d16 {
  grid-area: d16;
}

.d17 {
  grid-area: d17;
}

// //cuando ocupa una columna 2 filas
// .c1-r2{
//     grid-row: span 2;
//     grid-column: 1;

// }
// .c1-r1{
//     grid-row: 1;
//     height: 250px;
// }
// .c2-r2{
//     grid-row: span 2;
//     grid-column: span 2;
// }

.Codepen__title {
  font-family: "Roboto Condensed", sans-serif;
}
.Codepen__link {
  color: $color-dark;
}
.Codepen__item-hover-title-1 {
  top: 270px;
  display: none;
  position: absolute;
  padding-inline-start: 5px;
  height: 80px;
  width: 100%;
  color: $color-dark;
}
.Codepen__item-hover-title-2 {
  top: 570px;
  display: none;
  position: absolute;
  padding-inline-start: 5px;
  height: 80px;
  width: 100%;
  color: $color-dark;
}
.Codepen__item-hover-box-1 {
  top: 0;
  display: block;
  position: absolute;
  height: 220px;
  width: 100%;
}
.Codepen__item-hover-box-2 {
  top: 0;
  display: block;
  position: absolute;
  height: 520px;
  width: 100%;
}
.Codepen__item:hover {
  > .Codepen__item-hover-box-1,
  .Codepen__item-hover-box-2 {
    z-index: 999;
    box-shadow: 0rem 0rem 1rem $color-shadow;
    transition: 0.5s ease-in;
  }

  > .Codepen__item-hover-title-1 {
    top: 270px;
    display: block;
    color: $color-hover-text;
    background-color: $color-hover-titulo;
    > .Codepen__link {
      color: $color-hover-text;
    }
  }
  > .Codepen__item-hover-title-2 {
    top: 620px;
    display: block;
    color: $color-hover-text;
    background-color: $color-hover-titulo;
    > .Codepen__link {
      color: $color-hover-text;
    }
  }
}

$areas: (1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
@each $area in $areas {
  .grid-area--#{$area} {
    grid-area: $area;
  }
}
</style>
