<script>
  export default {
    props: {
      Get_card: {
        type:Function,
        required: true
      },
      My_cards_func: {
        type:Function,
        required: true
      }
    },
    data() {
      return {
        menu: false
      }
    },
    methods: {
      Burger_menu() {
        if (this.menu) {
          this.menu = false
        } else {this.menu = true}
      }
    }
  }
</script>

<template>
  <div class="wrapper">
    <ul class="buttons">
      <li class="get_buuton">
        <button type="button" @click="Get_card()">GET CARD</button>
      </li>
      <li class="cards_button">
        <button type="button" @click="My_cards_func()">MY CARDS</button>
      </li>
      <li class="games_button">
        <button type="button">GAMES</button>
      </li>
      <li class="craft_button">
        <button type="button">CRAFT</button>
      </li>
    </ul>
    <div class="burger_menu" :class="{ 'burger_action': menu }" @click="Burger_menu()">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="menu" :class="{ 'menu_action': menu }">
      <ul>
        <li>
          <button type="button" @click="My_cards_func()">MY CARDS</button>
        </li>
        <li>
          <button type="button">GAMES</button>
        </li>
        <li>
          <button type="button">CRAFT</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.menu {
  display: none;
  position: fixed;
  height: 100%;
  width: 30%;
  top: 0;
  right: -30%;
  background: #FFE3C2;
  border-left: 6px solid #cb9a51;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  transition: all 0.5s;
  z-index: 1;
}

.burger_menu {
  cursor: pointer;
  display: none;
  position: fixed;
  top: 35px;
  right: 40px;
  width: 60px;
  height: 25px;
  z-index: 2;
  padding-top: 15px;
}
.burger_menu span:nth-child(2) {
  display: block;
  width: 60px;
  height: 8px;
  border-radius: 5px;
  background: #CB9A51;
  transition: all 0.5s;
}
.burger_menu span:nth-child(1) {
  display: block;
  content: '';
  width: 60px;
  height: 8px;
  border-radius: 5px;
  background: #CB9A51;
  position: absolute;
  top: 30px;
  transition: all 0.5s;
}
.burger_menu span:nth-child(3) {
  display: block;
  content: '';
  width: 60px;
  height: 8px;
  border-radius: 5px;
  background: #CB9A51;
  position: absolute;
  top: 0px;
  transition: all 0.5s;
}
.burger_action span:nth-child(2) {
  opacity: 0;
}
.burger_action span:nth-child(3),
.burger_action span:nth-child(1) {
  top: 15px;
  transform: rotate(45deg);

}
.burger_action span:nth-child(1){
  transform: rotate(-45deg);
}
.buttons button, .menu button {
  font-size: 40px;
  background: #FFE3C2;
  border-radius: 15px;
  border: 6px solid #cb9a51;
  box-shadow: 5px 4px 10px 4px rgba(83, 83, 83, 0.2);
  color: #CB9A51;
  width: 250px;
  height: 75px;
  margin-right: 30px;
  transition: all 0.5s;
  cursor: pointer;
  letter-spacing: 2px;
  font-weight: 400;
  font-family: 'Bubblez';
  -webkit-text-stroke: 2px #252525;
}
.menu button {
  width: 200px;
  margin-right: 0;
  margin-bottom: 30px;
  font-size: 28px;
}
.buttons {
  display: flex;
  justify-content: center;
}
@media (max-width: 1200px ) {
  .buttons button {
    width: 200px;
    font-size: 30px;
    margin-right: 20px;
  }
}
@media (max-width: 960px ) {
  .menu {
    display: flex;
  }
  .burger_menu {
    display: block;
  }
  .cards_button,
  .games_button,
  .craft_button {
    display: none;
  }
}
@media (max-width: 760px ) {
.menu {
  width: 40%;
  right: -40%;
  }
}
@media (max-width: 560px) {
  .menu {
  width: 50%;
  right: -50%;
  }
}
@media (max-width: 420px) {
  .menu {
    width: 60%;
    right: -60%;
  }
  .burger_menu span:nth-child(1),
  .burger_menu span:nth-child(2),
  .burger_menu span:nth-child(3) {
    width: 40px;
    height: 5px;
  }
  .burger_menu span:nth-child(1) {
    top: 20px;
  }
  .burger_menu {
    padding-top: 10px;
    width: 40px;
    height: 15px;
    top: 30px;
  }
  .burger_action span:nth-child(3),
  .burger_action span:nth-child(1) {
    top: 10px;
  }
  .buttons button, .menu button {
    width: 175px;
    height: 50px;
    font-size: 25px;
  }
  .buttons {
    justify-content: left;
    margin-left: 30px;
  }
}
.menu_action {
  right: 0;
}
.buttons li:last-child button {
  margin-right: 0;
}
.menu li:last-child button {
  margin-bottom: 0;
}
.buttons button:hover {
  transform: scale(1.05) translateY(-5px);
}
.menu button:hover {
  transform: scale(1.05) translateY(-5px);
}

</style>