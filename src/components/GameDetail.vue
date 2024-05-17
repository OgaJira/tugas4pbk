<!-- src/components/GameDetail.vue -->
<template>
    <div class="game-detail">
      <h4>{{ game.title }}</h4>
      <p>{{ game.description }}</p>
      <p>Harga: {{ game.price }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['game']
  };
  </script>
  
  <style scoped>
  .game-detail {
    border: 1px solid #ddd;
    padding: 10px;
    margin: 10px 0;
  }
  </style>
  