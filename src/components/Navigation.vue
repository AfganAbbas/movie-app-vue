<template>
  <v-toolbar color="purple" dark app dense elevation="4">
    <v-toolbar-title>Movie App</v-toolbar-title>

    <v-text-field
      v-model="search"
      class="mx-6 shrink flex-end-xs-only"
      hide-details
      single-line
      append-icon="mdi-magnify"
      @click:append="testFunc"
    ></v-text-field>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-xs-only">
      <v-btn text to="/watch-list"> Watch list </v-btn>
      <v-btn text> Log in </v-btn>
      <v-btn text> Sign up </v-btn></v-toolbar-items
    >
  </v-toolbar>
</template>

<script>
export default {
  name: "Navigation",
  data() {
    return {
      search: "",
    };
  },
  methods: {
    testFunc() {
      console.log(this.search);
    },
  },
};
</script>

<style></style>
