<template>
  <table>
    <thead>
      <tr>
        <th>#</th>
        <th>Juego</th>
        <th>Eliminar juego de tu lista</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(game, index) in games" :key="index">
        <td>{{ index }}</td>
        <td>{{ game }}</td>
        <td><button class="btn-eliminar" @click="removeGame(index)">eliminar</button></td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: 'GameList',
  props: {
    games: Array
  },
  methods: {
    removeGame(index) {
      this.$emit('remove-game', index);
    }
  }
};
</script>

<style>
table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}
table, th, td {
  border: 1px solid #333;
}
th, td {
  padding: 10px;
  text-align: center;
}
th {
  background-color: #333;
  color: white;
}
.btn-eliminar {
  background-color: #ff4d4d;
  color: white;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
  border-radius: 3px;
}
.btn-eliminar:hover {
  background-color: #ff1a1a;
}
</style>