<script>
  export default {
    data() {
      return {
        id_card: '../../public/img/cards/010001.jpg',
        name: 'saypink!',
        type: 'Base card',
        rarity: 'Rare',
        fame: 'Fame: +150',
        color: '#8c92ed'
      }
    },
    props: {
      card: {
        type: Object,
        required: true
      },
      get_card: {
        type: Boolean,
        required: true
      },
      width: {
        type: Boolean,
        required: true
      },
      card_artist: {
        type: Boolean,
        required: true
      },
      card_info: {
        type: Boolean,
        required: true
      },
      card_flip: {
        type: Boolean,
        required: true
      },
      Card_flip: {
        type: Function,
        required: true
      }
    }
  }
</script>

<template>
  <div class="card" v-show="get_card" :class="{ 'flip': card_flip }" @click="Card_flip()">
    <img :src="card.bg" alt="" class="bg">
    <img :src="card.img" alt="" class="artist" v-show="card_artist">
    <div class="info" :style="{ '--color': card.color }" v-show="card_info">
      <h1 class="name">{{ card.name }}</h1>
      <p class="type">{{ card.type }}</p>
      <p class="rarity">{{ card.rarity }}</p>
      <p class="fame">{{ card.fame }}</p>
    </div>
  </div>
</template>

<style scoped>
  .flip {
    transform: rotateY(90deg) scale(1.15);
  }
  .card {
    width: 400px;
    height: 500px;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: auto;
    margin-top: 200px;
    cursor: pointer;
    transition: all 0.5s ease-in-out;
    padding: 0 30px;
    box-sizing: border-box;
  }

  .bg {
    position: absolute;
    top: 0;
    left: 0;
    z-index: -1;
    width: 100%;
    height: 100%;
  }
  .info {
    --color: #000;
    font-family: 'Bubblez';
    font-size: 50px;
    font-weight: 400;
    color: var(--color);
    text-align: center;
    letter-spacing: 2px;
    -webkit-text-stroke: 1px #252525;
    background-color: #ededed;
    border-radius: 20px;
  }
  .name {
    font-size: 50px;
    margin-bottom: 30px;
    font-weight: 400;
  }
  @media (max-width: 760px) {
    .card {
      width: 300px;
      height: 375px;
    }
    .artist {
      transform: scale(0.75)
    }
    .info {
      font-size: 35px;
    }
    .name {
      font-size: 30px;
    }
  }
  @media (max-width: 560px) {
    .card {
      width: 240px;
      height: 300px;
      margin-top: 75px;
    }
    .artist {
      transform: scale(0.6)
    }
    .info {
      font-size: 25px;
    }
    .name {
      font-size: 25px;
    }
  }
  @media (max-width: 420px) {
    .card {
      width: 160px;
      height: 200px;
    }
    .artist {
      transform: scale(0.4);
    }
  }
</style>