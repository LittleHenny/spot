<script>
import artist from './artist.vue'

  export default {
    components: { artist },
    data() {
      return {
        my_cards_array_sort: [],
        array_empty: false,
        btn_r: false,
        btn_l: true,
        now_card: 0,
      }
    },
    methods: {
      Btn_artist() {
        this.My_cards_show(false)
        this.Artist_show(true)
        this.my_cards_array_sort = []
        for (let card in this.my_cards_array) {
          if (this.my_cards_array[card].type == 'Artist') {
            this.my_cards_array_sort.push(this.my_cards_array[card])
          }
        }
        this.Check_top_bottom()
        if(this.my_cards_array_sort.length == 0) {
          this.array_empty = true
        } else this.array_empty = false
      },
      Btn_singlees() {
        this.My_cards_show(false)
        this.Artist_show(true)
        this.my_cards_array_sort = []
        for (let card in this.my_cards_array) {
          if (this.my_cards_array[card].type == 'Single') {
            this.my_cards_array_sort.push(this.my_cards_array[card])
          }
        }
        this.Check_top_bottom()
        if(this.my_cards_array_sort.length == 0) {
          this.array_empty = true
        } else this.array_empty = false
      },
      Btn_albums() {
        this.My_cards_show(false)
        this.Artist_show(true)
        this.my_cards_array_sort = []
        for (let card in this.my_cards_array) {
          if (this.my_cards_array[card].type == 'Album') {
            this.my_cards_array_sort.push(this.my_cards_array[card])
          }
        }
        this.Check_top_bottom()
        if(this.my_cards_array_sort.length == 0) {
          this.array_empty = true
        } else this.array_empty = false
      },
      Btn_signs() {
        this.My_cards_show(false)
        this.Artist_show(true)
        this.my_cards_array_sort = []
        for (let card in this.my_cards_array) {
          if (this.my_cards_array[card].type == 'Sign') {
            this.my_cards_array_sort.push(this.my_cards_array[card])
          }
        }
        this.Check_top_bottom()
        if(this.my_cards_array_sort.length == 0) {
          this.array_empty = true
        } else this.array_empty = false
      },
      Btn_evo() {
        this.My_cards_show(false)
        this.Artist_show(true)
        this.my_cards_array_sort = []
        for (let card in this.my_cards_array) {
          if (this.my_cards_array[card].type == 'EVO') {
            this.my_cards_array_sort.push(this.my_cards_array[card])
          }
        }
        this.Check_top_bottom()
        if(this.my_cards_array_sort.length == 0) {
          this.array_empty = true
        } else this.array_empty = false
      },
      Check_top() {
        if(this.now_card + 1 == this.my_cards_array_sort.length) {
          this.btn_r = true
        } else this.btn_r = false
      },
      Check_bottom() {
        if(this.now_card == 0) {
          this.btn_l = true
        } else this.btn_l = false
      },
      Check_top_bottom() {
        this.now_card = 0
        if(this.my_cards_array_sort.length == 1) {
          console.log(this.my_cards_array_sort);
          this.btn_r = true
          this.btn_l = true
        } else {
          this.btn_r = false
          this.btn_l = true
        }
      },
      Next_card() {
        this.Card_flip_vert()
        setTimeout(() => {
          this.now_card++
          this.Check_top()
          this.Check_bottom()
        }, 500)
      },
      Past_card() {
        this.Card_flip_vert()
        setTimeout(() => {
          this.now_card--
          this.Check_top()
          this.Check_bottom()
        }, 500)
      },
    },
    props: {
      My_cards_show: {
        type: Function,
        required: true
      },
      my_cards_show: {
        type: Boolean,
        required: true
      },
      my_cards_array: {
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
      Artist_show: {
        type: Function,
        required: true
      },
      artist_show: {
        type: Boolean,
        required: true
      },
      Card_flip_vert: {
        type: Function,
        required: true
      },
      card_flip_vert: {
        type: Boolean,
        required: true
      }
    }
  }
</script>
<template>
  <div class="wrapper">
    <div class="buttons" v-show="my_cards_show">
      <button type="button" class="Artist" @click="Btn_artist()">Artist</button>
      <button type="button" class="Singles" @click="Btn_singlees()">Singlees</button>
      <button type="button" class="Albums" @click="Btn_albums()">Albums</button>
      <button type="button" class="Signs" @click="Btn_signs()">Signs</button>
      <button type="button" class="EVO" @click="Btn_evo()">EVO</button>
    </div>
    <div v-show="artist_show">
      <artist :my_cards_array_sort="my_cards_array_sort" :card_artist="card_artist"
      :card_info="card_info" :card_flip="card_flip" :Card_flip="Card_flip"
      :Card_flip_vert="Card_flip_vert" :card_flip_vert="card_flip_vert"
      :array_empty="array_empty" :btn_r="btn_r" :btn_l="btn_l" :Check_top="Check_top"
      :Check_bottom="Check_bottom" :now_card="now_card" :Next_card="Next_card"
      :Past_card="Past_card"/>
    </div>
  </div>
</template>
<style scoped>
  button {
    font-family: 'Bubblez';
    font-size: 50px;
    background: #FFE3C2;
    border-radius: 15px;
    border: 6px solid #cb9a51;
    box-shadow: 5px 4px 10px 4px rgba(83, 83, 83, 0.2);
    color: #CB9A51;
    font-weight: 400;
    width: 300px;
    height: 75px;
    margin-top: 30px;
    transition: all 0.5s;
    cursor: pointer;
    letter-spacing: 2px;
    -webkit-text-stroke: 2px #252525;
  }

  button:hover {
    transform: scale(1.05) translateY(-5px);
  }
  .buttons {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 200px;
  }
  @media (max-width: 560px) {
    .buttons {
      margin-top: 75px
    }
    button {
      width: 200px;
      font-size: 30px;
      margin-top: 15px;
    }
  }
  button:first-child {
    margin-top: 0;
  }
</style>