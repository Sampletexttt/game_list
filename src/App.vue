<template>
  <div id="app">
    <Games v-bind:games="games" v-on:del-game="deleteGame" />
  </div>
</template>

<script>
import Games from './components/Games';

export default {
  name: "app",
  components: {
    Games
  },
  data() {
    return{
      Games: [
        {
          id: 1,
          title: "Game One",
          completed: false
        },
        {
          id: 2,
          title: "Game Two",
          completed: true
        },
        {
          id: 3,
          title: "Game Three",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteGame(id) {
      this.games = this.games.filter(game => game.id !== id);
    }
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
</style>
