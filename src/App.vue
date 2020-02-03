<template>
  <div id="app">
    <Header />
    <AddGame v-on:add-Game="addGame" />
    <Games v-bind:games="games" v-on:del-game="deleteGame" />
  </div>
</template>

<script>
import Header from './components/layout/Header'
import Games from './components/Games';
import AddGame from './components/AddGame';
import axios from 'axios';

export default {
  name: "app",
  components: {
    Header,
    Games,
    AddGame
  },
  data() {
    return{
      games: []
    }
  },
  methods: {
    deleteGame(id) {
      this.games = this.games.filter(game => game.id !== id);
    },
    addGame(newGame) {
      this.games = [...this.games, newGame];
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos')
    .then(res => this.games = res.data)
      .catch(err => console.log(err));
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
