<script setup>
import game_tel from './components/game_tel.vue'
</script>

<template>
  <section class="menu" v-if="game_select == 0">
    <h1 class="h1_home">WAIT AND SEE !</h1>
    <div class="menu_select">
      <div class="menu_game_mode">
        <input class="game_mode_select pop_menu_1" type="button" value="Jeu IRL" @click="game_phone">
      </div>
      <div class="menu_game_mode">
        <input class="game_mode_select pop_menu_2" type="button" value="WIP">
      </div>
    </div>
  </section>
  <game_tel v-if="game_select == 1"></game_tel>
</template>
  
<script>
  export default {
    methods: {

      game_phone() {
        this.game_select = 1
      },
    },
    data() {
        return {
          game_select : 0
        }
    },
  }
</script>

<style>

  /* @import url(https://fr.allfont.net/allfont.css?fonts=anime-ace-20-bb); */

  * {
    font-family: 'Patrick Hand', cursive;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    background-image: url('./assets/img/background/plateau_bois.jpg');
    background-size: cover;
    background-repeat: no-repeat;
  }

  .menu {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .h1_home {
    font-size: 5rem;
    margin-bottom: 3rem;
    text-align: center;
  }

  .menu_select {
    height: 30rem;
    width: 80%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
  }

  .menu_game_mode {
    width: 30rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .game_mode_select {
    padding: 2rem;
    font-size: 3rem;
    border-radius: 5rem;
    border: 0;
    cursor: pointer;
  }

  .pop_menu_1 {
    animation: pop_menu_1 2s infinite;
  }

  .pop_menu_2 {
    animation: pop_menu_2 2s infinite;
  }

  @keyframes pop_menu_1 {
    0% {
      padding: 2rem;
      font-size: 3rem;
    }

    5% {
      padding: 2rem;
      font-size: 4rem;
    }

    10% {
      padding: 2rem;
      font-size: 3rem;
    }
  }

  @keyframes pop_menu_2 {
    50% {
      padding: 2rem;
      font-size: 3rem;
    }

    55% {
      padding: 2rem;
      font-size: 4rem;
    }

    60% {
      padding: 2rem;
      font-size: 3rem;
    }
  }

  @media screen and (max-width: 500px) {

    .h1_home {
      font-size: 3rem;
    }

    .menu_select {
      height: 20rem;
    }

    .menu_game_mode {
      height: 10rem;
    }

    .game_mode_select {
      padding: 1rem;
      font-size: 2rem;
      border-radius: 5rem;
    }

    @keyframes pop_menu_1 {
      0% {
        padding: 1rem;
        font-size: 2rem;
      }
      10% {
        padding: 2rem;
        font-size: 3rem;
      }
      20% {
        padding: 1rem;
        font-size: 2rem;
      }
    }

    @keyframes pop_menu_2 {
      60% {
        padding: 1rem;
        font-size: 2rem;
      }
      70% {
        padding: 2rem;
        font-size: 3rem;
      }
      80% {
        padding: 1rem;
        font-size: 2rem;
      }
    }
    
  }

</style>
