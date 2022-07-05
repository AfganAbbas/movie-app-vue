<template>
  <v-card>
    <v-card class="mx-auto" max-width="150" tile>
      <v-img height="200px" :src="movie"></v-img>
    </v-card>
  </v-card>
</template>

<script>
export default {
  name: "Movie",
  props: {
    movie: String,
  },
};
</script>

<style></style>
