<!-- Common #fbf8f4-->



<script>
  import main_menu from './components/main_menu.vue'
  import welcome_logo from './components/welcome_logo.vue'
  import get_card from './components/get_card.vue'
  import my_cards from './components/my_cards/my_cards.vue'
  export default {
    components: { main_menu, welcome_logo, get_card, my_cards },
    data() {
      return {
        time_until_try: 0,
        error_not_attempts: false,
        attempts: 1,
        card_flip_vert: false,
        artist_show: false,
        my_cards_show: false,
        my_cards_array: [

        ],
        width: true,
        card: {},
        welcome: true,
        get_card: false,
        card_artist: true,
        card_info: false,
        card_flip: false,
        now_card: {
          type: 1,
          rarity: 1,
        },
        artist_card: {
          common_card: [

          ],
          rare_card: [
            {
              name: 'cold carti',
              type: 'Artist',
              rarity: 'Rare',
              fame: 'Fame: +150',
              bg: '/public/img/cards/bg/rare.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            }
          ],
          epic_card: [

          ],
          legendary_card: [

          ]
        },
        single_card: {
          common_card: [

          ],
          rare_card: [
            {
              name: 'cold carti - 03',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_03.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - болезнь',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_болезнь.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - больше, чем',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: 'public/img/cards/bg/cold_carti_больше_чем.png',
              img: 'public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - быть чатью',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_быть_частью.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - вряд ли ты вывезешь',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_вряд_ли_ты_вывезешь.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - дом',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_дом.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - если ты забыла как дыщать',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_если_ты_забыла_как_дышать.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - забывай',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_забывай.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - звёзды плачут',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_звёзды_плачут.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - кислород',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_кислород.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - кто ты такая?',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_кто_ты_такая.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - Мокрая',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_мокрая.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - море',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_море.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - не выдыхай',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_не_выдыхай.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - не говори мне',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_не_говори_мне.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
            {
              name: 'cold carti - не хочу',
              type: 'Single',
              rarity: 'Rare',
              fame: 'Fame: +200',
              bg: '/public/img/cards/bg/cold_carti_не_хочу.png',
              img: '/public/img/cards/artists/cold_carti.png',
              color: '#BCC3FF',
            },
          ],
          epic_card: [

          ],
          legendary_card: [

          ]
        },
        album_card: {
          common_card: [

          ],
          rare_card: [

          ],
          epic_card: [

          ],
          legendary_card: [

          ]
        },
        signature_card: {
          common_card: [

          ],
          rare_card: [

          ],
          epic_card: [

          ],
          legendary_card: [

          ]
        },
        clip_card: {
          common_card: [

          ],
          rare_card: [

          ],
          epic_card: [

          ],
          legendary_card: [

          ]
        },
      }
    },
    methods: {
      My_cards_show(swap) {
        if(swap) {
          this.my_cards_show = true
        } else {
          this.my_cards_show = false
        }
      },
      Artist_show(swap) {
        if(swap) {
          this.artist_show = true
        } else {
          this.artist_show = false
        }
      },
      My_cards_func() {
        this.welcome = false
        this.get_card = false
        this.my_cards_show = true
        this.artist_show = false

        this.card_artist = true
        this.card_info = false
      },
      Get_card() {
        this.welcome = false
        this.my_cards_show = false
        this.artist_show = false
        
        this.card_artist = true
        this.card_info = false
        
        if (this.attempts == 0) {
          this.get_card = false
          this.error_not_attempts = true
          return
        }
        this.error_not_attempts = false
        this.get_card = true
        this.attempts--
        if (this.attempts == 0) {
          this.time_until_try = 60
          let timer = setInterval(() => {
            this.time_until_try--
          }, 60000)

          setTimeout(() => {
            this.attempts++
            clearInterval(timer)
          }, 3600000)
        }
        // let type_card =  Math.floor(Math.random() * 100)
        // if (type_card <= 80) {
        //   this.now_card.type = 0
        // } else if (type_card <= 90) {
        //   this.now_card.type = 1
        // } else if (type_card <= 95) {
        //   this.now_card.type = 2
        // } else if (type_card <= 98) {
        //   this.now_card.type = 3
        // } else {
        //   this.now_card.type = 4
        // }
        // let rarity_card =  Math.floor(Math.random() * 100)
        // if (rarity_card <= 70) {
        //   this.now_card.rarity = 0
        // } else if (rarity_card <= 85) {
        //   this.now_card.rarity = 1
        // } else if (rarity_card <= 95) {
        //   this.now_card.rarity = 2
        // } else {
        //   this.now_card.rarity = 3
        // }
        if (this.now_card.type == 0) {
          if (this.now_card.rarity == 0) {
            let len = this.artist_card.common_card.length
            this.card = this.artist_card.common_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else if (this.now_card.rarity == 1) {
            let len = this.artist_card.rare_card.length
            this.card = this.artist_card.rare_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else if (this.now_card.rarity == 2) {
            let len = this.artist_card.epic_card.length
            this.card = this.artist_card.epic_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else {
            let len = this.artist_card.legendary_card.length
            this.card = this.artist_card.legendary_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          }
        } else if (this.now_card.type == 1) {
          if (this.now_card.rarity == 0) {
            let len = this.single_card.common_card.length
            this.card = this.single_card.common_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else if (this.now_card.rarity == 1) {
            let len = this.single_card.rare_card.length
            this.card = this.single_card.rare_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else if (this.now_card.rarity == 2) {
            let len = this.single_card.epic_card.length
            this.card = this.single_card.epic_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else {
            let len = this.single_card.legendary_card.length
            this.card = this.single_card.legendary_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          }
        } else if (this.now_card.type == 2) {
          if (this.now_card.rarity == 0) {
            let len = this.album_card.common_card.length
            this.card = this.album_card.common_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else if (this.now_card.rarity == 1) {
            let len = this.album_card.rare_card.length
            this.card = this.album_card.rare_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else if (this.now_card.rarity == 2) {
            let len = this.album_card.epic_card.length
            this.card = this.album_card.epic_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else {
            let len = this.album_card.legendary_card.length
            this.card = this.album_card.legendary_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          }
        } else if (this.now_card.type == 3) {
          if (this.now_card.rarity == 0) {
            let len = this.signature_card.common_card.length
            this.card = this.signature_card.common_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else if (this.now_card.rarity == 1) {
            let len = this.signature_card.rare_card.length
            this.card = this.signature_card.rare_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else if (this.now_card.rarity == 2) {
            let len = this.signature_card.epic_card.length
            this.card = this.signature_card.epic_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else {
            let len = this.signature_card.legendary_card.length
            this.card = this.signature_card.legendary_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          }
        } else {
          if (this.now_card.rarity == 0) {
            let len = this.clip_card.common_card.length
            this.card = this.clip_card.common_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else if (this.now_card.rarity == 1) {
            let len = this.clip_card.rare_card.length
            this.card = this.clip_card.rare_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else if (this.now_card.rarity == 2) {
            let len = this.clip_card.epic_card.length
            this.card = this.clip_card.epic_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          } else {
            let len = this.clip_card.legendary_card.length
            this.card = this.clip_card.legendary_card[Math.floor(Math.random() * len)]
            this.my_cards_array.push(this.card)
            localStorage.setItem('my_cards', JSON.stringify(this.my_cards_array))
          }
        }
      },
      Card_flip() {
        if(this.card_flip) {this.card_flip = false} else {this.card_flip = true}
        setTimeout(() => {
          if(this.card_artist) {
            this.card_artist = false
            this.card_info = true
          } else {
            this.card_artist = true
            this.card_info = false
          }
          if(this.card_flip) {this.card_flip = false} else {this.card_flip = true}
        }, 500)
      },
      Card_flip_vert() {
        if(this.card_flip_vert) {this.card_flip_vert = false} else {this.card_flip_vert = true}
        setTimeout(() => {
          if(this.card_flip_vert) {this.card_flip_vert = false} else {this.card_flip_vert = true}
        }, 500)
      },
    },
    mounted() {
      if (localStorage.getItem('my_cards')) {
        this.my_cards_array = JSON.parse(localStorage.getItem('my_cards'))
      }
    }
  }
</script>

<template>
  <main_menu :Get_card="Get_card" :width="width" :My_cards_func="My_cards_func"/>
  <welcome_logo :welcome="welcome"/>
  <get_card :card="card" :get_card="get_card" :card_artist="card_artist" :card_info="card_info"
  :card_flip="card_flip" :Card_flip="Card_flip"/>
  <my_cards :My_cards_show="My_cards_show" :my_cards_array="my_cards_array" :card_artist="card_artist"
  :card_info="card_info" :card_flip="card_flip" :Card_flip="Card_flip" :my_cards_show="my_cards_show"
  :Artist_show="Artist_show" :artist_show="artist_show" :Card_flip_vert="Card_flip_vert" :card_flip_vert="card_flip_vert"/>
  <p class="error_not_attempts" v-show="error_not_attempts">You've run out of tries. until next {{ time_until_try }} minutes</p>
</template>

<style scoped>
  .error_not_attempts {
    font-size: 80px;
    color: #CB9A51;
    text-align: center;
    letter-spacing: 2px;
    font-weight: 500;
    font-family: 'Bubblez';
    -webkit-text-stroke: 3px #252525;
    margin-top: 250px;
  }
  @media (max-width: 960px) {
    .error_not_attempts {
      font-size: 60px;
      margin-top: 200px;
    }
  }
  @media (max-width: 760px) {
    .error_not_attempts {
      font-size: 50px;
      margin-top: 150px;
    }
  }
  @media (max-width: 420px) {
    .error_not_attempts {
      font-size: 40px;
      margin-top: 100px;
    }
  }
</style>
