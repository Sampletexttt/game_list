<template>
  <div id="app">
    <Games />
  </div>
</template>

<script>
import Games from './components/Games';

export default {
  name: 'app',
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
