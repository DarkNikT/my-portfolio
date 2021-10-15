<template>
  <v-container class="ListGrid__container">
    <project-item
      v-for="codepen in codepens"
      :key="codepen.id"
      :propsPen="codepen"
      :heightImage="350"
      :username="username"
    ></project-item>
    <!-- <project-item :propsPen="codepens[0]" :heightImage="300"></project-item> -->
  </v-container>
</template>

<script>
import ProjectItem from "./../components/ProjectItem.vue";
export default {
  name: "Test",
  mounted() {
    console.log(this.codepens);
  },
  data() {
    return {};
  },
  props: ["codepens", "username"],
  methods: {},
  components: { ProjectItem },
};
</script>

<style lang="scss" scoped>
.ListGrid__container {
  justify-content: center;

  @media (min-width: 768px) {
    display: grid;
    grid-template-columns: repeat(3, 350px);
    grid-template-rows: repeat(6, 350px);
    gap: 0px 0px;
    grid-auto-flow: row dense;
    grid-template-areas:
      "d1 d1 d2"
      "d1 d1 d3"
      "d5 d4 d4"
      "d6 d7 d8"
      "d9 d9 d10"
      "d9 d9 d11"
      "d13 d12 d12"
      "d14 d12 d12"
      "d15 d16 d17";
  }

  @media (max-width: 768px) {
    display: flex;
    flex-direction: column;
  }
}

.span-row-2 {
  grid-row-start: auto;
  grid-row-end: span 2;
}
</style>
