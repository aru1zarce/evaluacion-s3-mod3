<template>
  <div id="app">
    <div class="header">
      Tienda Bit-Game
    </div>
    <div class="content">
      <div class="welcome">
        <h1>¡Bienvenido!</h1>
        <p>A continuación encontrarás la lista de los juegos que prefieres</p>
      </div>
      <GameList :games="games" @remove-game="removeGame" />
    </div>
  </div>
</template>

<script>
import GameList from './components/GameList.vue';

export default {
  name: 'App',
  components: {
    GameList
  },
  data() {
    return {
      games: ["Arena of valor", "Pokemon Unite", "Donkey Kong", "Heroes of the storm", "Valorant"]
    };
  },
  methods: {
    removeGame(index) {
      this.games.splice(index, 1);
    }
  }
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
}
.header {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 10px 0;
  font-size: 24px;
}
.content {
  margin: 20px;
}
.welcome {
  background-color: #e0f7fa;
  padding: 20px;
  border-radius: 5px;
  margin-bottom: 20px;
}
.welcome h1 {
  margin: 0;
  font-size: 24px;
}
.welcome p {
  margin: 10px 0 0;
  font-size: 16px;
}
</style>