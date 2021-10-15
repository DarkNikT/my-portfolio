<template>
  <div class="row item-line">
    <div class="pointer col-md-2">
      <h1>{{ year }}</h1>
    </div>
    <div class="event col-md-8">
      <h1>{{ TitleEvent }}</h1>
      <p>{{ TextEvent }}</p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
  props: ["year", "TitleEvent", "TextEvent"],
};
</script>
<style lang="scss" scoped>
@import "@/assets/styles/global.scss";
.item-line {
  border-width: 5% 0 5% 0;
  border-color: $color-black;
  border-style: solid;
  margin-block: 2rem;
}
.pointer {
  color: white;
  display: flex;
  align-items: center;
  position: relative;
  &::after {
    position: absolute;
    left: 60%;
    margin-inline: 1rem;
    content: "";
    width: 32px;
    height: 32px;
    // background-color: white;
    border: 5px solid white;
    border-radius: 50%;
  }
}
.event {
  background-color: $color-gray;
  padding: 0 0 0;
  width: 100%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  & h1 {
    padding: 5px;
    font-size: 1rem;
    width: 100%;
    background-color: white;
  }
  & p {
    padding: 5px;
    font-size: 1rem;
    width: 100%;
    color: $color-gray-l;
  }
}
</style>
