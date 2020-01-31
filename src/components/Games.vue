<template>
  <div>
<div v-bind:key="game.id" v-for="game in games">
  <h3>{{game.title}}</h3>
</div>
  </div>
</template>

<script>
export default{
name: "Games",
props: ["games"]
}
</script>

<style scoped>

</style>
