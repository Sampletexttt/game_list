<template>
  <div>
    <form @submit="addGame">
      <input type="text" v-model="title" name="title" placeholder="Add Game...">
      <input type="submit" value="Submit" class="btn">
    </form>
  </div>
</template>

<script>
  import uuid from 'uuid';
  export default {
    name: "AddGame",
    data() {
      return {
        title: ''
      }
    },
    methods: {
      addGame(e) {
        e.preventDefault();
        const newGame = {
          id: uuid.v4(),
          title: this.title,
          completed: false
        }
        // send up to parent
        this.$emit('add-Game', newGame);

        this.title = '';
      }
    }
  }
</script>

<style scoped>
  form {
    display: flex;
  }

  input[type="text"] {
    flex: 10;
    padding: 5px;
  }

  input[type="submit"] {
    flex: 2;
  }
</style>
