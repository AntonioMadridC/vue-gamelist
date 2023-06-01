<template>
  <div id="app">
    <nav
      class="navbar bg-dark border-bottom border-bottom-dark mb-5 justify-content-center"
      data-bs-theme="dark"
    >
      <h1 class="text-center"><a class="link-light link-underline link-underline-opacity-0" href="#">Tienda Bit-Game</a></h1>
    </nav>

    <div class="alert alert-info mb-5" role="alert">
      <h1>¡Bienvenido!</h1>
      <hr>
      <p>A continuación encontrarás la lista de tus juegos favoritos</p>
    </div>

    <div class="container">
      <FavoriteGames :games="games" @remove="removeGame"></FavoriteGames>
    </div>
  </div>
</template>

<script>
import FavoriteGames from "./components/favoriteGames.vue";

export default {
  name: "App",
  components: {
    FavoriteGames,
  },
  data: function () {
    return {
      games: [
        "Arena of valor",
        "Pokemon Unite",
        "Donkey Kong",
        "Heroes of the storm",
        "Valorant",
      ],
    };
  },
  methods: {
    removeGame(index) {
      this.games.splice(index, 1);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0;
}
</style>
