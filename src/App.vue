<template>
  <v-app>
    <Navigation />

    <!-- <v-autocomplete></v-autocomplete> -->
    <v-main>
      <Latest />
      <Popular />
      <router-view></router-view>
      <v-container v-for="i in 6" :key="i" class="grey lighten-5">
        <v-row class="my-4" no-gutters style="height: 150px">
          <v-col v-for="n in 5" :key="n">
            <Movie :movie="movies[i].download_url" />
          </v-col>
        </v-row>
      </v-container>
    </v-main>
    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>

<script>
import Movie from "./components/Movie.vue";
import Navigation from "./components/Navigation.vue";
import Popular from "./components/Popular.vue";
import Latest from "./components/Latest.vue";

export default {
  name: "App",

  data: () => ({
    movies: [],
  }),
  mounted() {
    fetch("https://picsum.photos/v2/list")
      .then((response) => response.json())
      .then((resp) => {
        this.movies = resp;
        console.log(this.movies);
      })
      .catch((err) => console.log(err));
  },
  components: {
    Movie,
    Navigation,
    Latest,
    Popular,
  },
  methods: {},
};
</script>
