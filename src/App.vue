<template>
  <div id="app">
    <Header @selectChanged="setGenre" :genres="genresList"/>
    <Main :filterGenre="selectGenre" @genresListCreated="setGenresList"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main
  },
  data: function() {
    return {
      selectGenre: '',
      genresList: []
    };
  },
  methods: {
    setGenre: function(genre) {
      this.selectGenre = genre;
    },
    setGenresList: function(genres) {
      this.genresList = genres;
    }
  }
};
</script>

<style lang="scss">
@import "./styles/general";
</style>
