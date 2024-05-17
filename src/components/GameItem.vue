<!-- src/components/GameItem.vue -->
<template>
    <div class="game-item">
      <h3 @click="toggleDetails">{{ game.name }}</h3>
      <div v-if="showDetails">
        <slot></slot>
        <game-detail v-for="detail in game.details" :key="detail.id" :game="detail"></game-detail>
      </div>
    </div>
  </template>
  
  <script>
  import GameDetail from './GameDetail.vue';
  
  export default {
    components: {
      GameDetail
    },
    props: ['game'],
    data() {
      return {
        showDetails: false
      };
    },
    methods: {
      toggleDetails() {
        this.showDetails = !this.showDetails;
        this.$emit('game-selected', this.game);
      }
    }
  };
  </script>
  
  <style scoped>
  .game-item {
    border: 1px solid #ccc;
    padding: 10px;
    margin: 10px 0;
    cursor: pointer;
  }
  .game-item:hover {
    background-color: #f0f0f0;
  }
  </style>
  