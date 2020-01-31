<template>
  <div class="game-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{game.title}}
      <button @click="$emit('del-game', game.id)" class="del">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name:"GameItem",
  props: ["game"],
  methods: {
    markComplete() {
      this.game.completed = !this.game.completed;
    }
  }
}
</script>

<style scoped>
  .game-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }

  .is-complete {
    text-decoration: line-through;
  }

  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
</style>
