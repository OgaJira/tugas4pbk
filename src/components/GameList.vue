<!-- src/components/GameList.vue -->
<template>
    <div class="game-list">
      <h2>Daftar Game</h2>
      <game-item
        v-for="game in games"
        :key="game.id"
        :game="game"
        @game-selected="handleGameSelected"
      >
        <template v-slot>
          <p>Detail untuk {{ game.name }}</p>
        </template>
      </game-item>
      <p v-if="selectedGame">
        Game terpilih: {{ selectedGame.name }}
      </p>
    </div>
  </template>
  
  <script>
  import GameItem from './GameItem.vue';
  
  export default {
    components: {
      GameItem
    },
    data() {
      return {
        games: [
          { id: 1, name: 'The Legend of Zelda', details: [
              { id: 1, title: 'Breath of the Wild', description: 'Open world action-adventure game', price: 'Rp 750.000' },
              { id: 2, title: 'Ocarina of Time', description: 'Action-adventure game', price: 'Rp 500.000' }
            ]
          },
          { id: 2, name: 'Super Mario', details: [
              { id: 1, title: 'Super Mario Odyssey', description: '3D platform game', price: 'Rp 700.000' },
              { id: 2, title: 'Super Mario Galaxy', description: 'Platformer game', price: 'Rp 650.000' }
            ]
          },
          { id: 3, name: 'Final Fantasy', details: [
              { id: 1, title: 'Final Fantasy VII', description: 'Role-playing game', price: 'Rp 800.000' },
              { id: 2, title: 'Final Fantasy XV', description: 'Action role-playing game', price: 'Rp 850.000' }
            ]
          },
          { id: 4, name: 'Resident Evil', details: [
              { id: 1, title: 'Resident Evil 2', description: 'Survival horror game', price: 'Rp 750.000' },
              { id: 2, title: 'Resident Evil Village', description: 'Survival horror game', price: 'Rp 850.000' }
            ]
          },
        ],
        selectedGame: null,
      };
    },
    methods: {
      handleGameSelected(game) {
        this.selectedGame = game;
      }
    }
  };
  </script>
  
  <style scoped>
  .game-list {
    width: 300px;
    margin: 0 auto;
  }
  </style>
  