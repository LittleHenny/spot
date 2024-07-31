<script>
  export default {
    data() {
      return {
        

      }
    },
    methods: {
      BG() {
        if (this.my_cards_array_sort.length != 0) {
          return this.my_cards_array_sort[this.now_card].bg
        } else return
      },
      IMG() {
        if (this.my_cards_array_sort.length != 0) {
          return this.my_cards_array_sort[this.now_card].img
        } else return
      },
      Color() {
        if (this.my_cards_array_sort.length != 0) {
          return this.my_cards_array_sort[this.now_card].color
        } else return
      },
      Name() {
        if (this.my_cards_array_sort.length != 0) {
          return this.my_cards_array_sort[this.now_card].name
        } else return
      },
      Type() {
        if (this.my_cards_array_sort.length != 0) {
          return this.my_cards_array_sort[this.now_card].type
        } else return
      },
      Rarity() {
        if (this.my_cards_array_sort.length != 0) {
          return this.my_cards_array_sort[this.now_card].rarity
        } else return
      },
      Fame() {
        if (this.my_cards_array_sort.length != 0) {
          return this.my_cards_array_sort[this.now_card].fame
        } else return
      },
    },
    props: {
      my_cards_array_sort: {
        type: Object,
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
      },
      Card_flip_vert: {
        type: Function,
        required: true
      },
      card_flip_vert: {
        type: Boolean,
        required: true
      },
      array_empty: {
        type: Boolean,
        required: true
      },
      btn_r: {
        type: Boolean,
        required: true
      },
      btn_l: {
        type: Boolean,
        required: true
      },
      now_card: {
        type: Number,
        required: true
      },
      Next_card: {
        type:Function,
        required: true
      },
      Past_card: {
        type:Function,
        required: true
      },
    }
  }
</script>

<template>
  <p class="array_empty" v-show="array_empty">You don't have this type of cards</p>
  <div class="main_wrapper" v-show="!array_empty">
    <p class="quantity">{{ now_card + 1 }}/{{ my_cards_array_sort.length }}</p>
    <div class="wrapper">
      <button class="btn_left" :class="{ 'none': btn_l}" :disabled="btn_l" @click="Past_card()"><</button>
      <div class="card" :class="{ 'flip': card_flip, 'flip_vert': card_flip_vert }" @click="Card_flip()">
        <img :src="BG()" alt="" class="bg">
        <img :src="IMG()" alt="" class="artist" v-show="card_artist">
        <div class="info" :style="{ '--color': Color() }" v-show="card_info">
          <h1 class="name">{{ Name() }}</h1>
          <p class="type">{{ Type() }}</p>
          <p class="rarity">{{ Rarity() }}</p>
          <p class="fame">{{ Fame() }}</p>
        </div>
      </div>
      <button class="btn_right" :class="{ 'none': btn_r}" :disabled="btn_r" @click="Next_card()">></button>
    </div>
  </div>
</template>

<style scoped>
.array_empty {
  font-family: 'Bubblez';
    font-size: 70px;
    font-weight: 400;
    color: #cb9a51;
    -webkit-text-stroke: 2px #252525;
    text-align: center;
    margin-top: 400px;
}
  .none {
    opacity: 0;
    cursor: auto;
  }
.quantity {
    font-family: 'Bubblez';
    font-size: 70px;
    font-weight: 400;
    color: #cb9a51;
    -webkit-text-stroke: 2px #252525;
    text-align: center;
    margin-top: 75px;
}
.flip_vert {
  transform: rotateX(90deg) scale(1.15);
}
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
    cursor: pointer;
    transition: all 0.5s ease-in-out;
    margin: 0 150px;
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
    -webkit-text-stroke: 2px #252525;
    background-color: #ededed;
    border-radius: 20px;
  }
  .name {
    font-size: 50px;
    margin-bottom: 30px;
    font-weight: 400;
  }
  button {
    padding: 10px 20px;
    background: #FFE3C2;
    border: 6px solid #cb9a51;
    font-family: 'Bubblez';
    font-size: 50px;
    font-weight: 400;
    border-radius: 10px;
    cursor: pointer;
    transition: all 0.5s;
    color: #cb9a51;
    letter-spacing: 2px;
    -webkit-text-stroke: 2px #252525;
  }
  button:hover {
    transform: scale(1.05) translateY(-5px);
  }
  .wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 75px;
  }
  @media (max-width: 960px) {
    .card {
      margin: 0 50px;
    }
    .wrapper {
    margin-top: 50px;
    }
    .quantity {
    margin-top: 50px;
    }
  }
  @media (max-width: 760px) {
    .card {
      width: 300px;
      height: 375px;
      margin: 0 30px;
    }
    .artist {
      transform: scale(0.75)
    }
    button {
      padding: 5px 15px;
    }
    .info {
      font-size: 35px;
    }
    .name {
      font-size: 35px;
    }
  }
  @media (max-width: 560px) {
    .card {
      width: 240px;
      height: 300px;
      margin: 0 20px;
    }
    .artist {
      transform: scale(0.6)
    }
    button {
      padding: 0px 10px;
    }
    .info {
      font-size: 25px;
    }
    .name {
      font-size: 25px;
    }
    .wrapper {
    margin-top: 25px;
    }
    .quantity {
    margin-top: 25px;
    }
  }
  @media (max-width: 420px) {
    .card {
      width: 160px;
      height: 200px;
      margin: 0 15px;
    }
    .artist {
      transform: scale(0.4)
    }
    button {
      font-size: 35px;
      border: 4px solid #cb9a51;
    }
    .quantity {
      font-size: 50px;
    }
  }
</style>