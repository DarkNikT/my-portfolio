<template>
  <div class="about">
    <h1 class="">This is an about page</h1>
    <v-row>
      <profile-card></profile-card>
    </v-row>
  </div>
</template>
<script>
import ProfileCard from "./../components/ProfileCard.vue";
export default {
  components: {
    ProfileCard,
  },
};
</script>
