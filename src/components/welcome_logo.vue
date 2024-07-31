<script>
  export default {
    props: {
      welcome: {
        type: Boolean,
        required: true
      }
    }
  }
</script>

<template>
  <div class="wrapper" v-show="welcome">
    <h1>SPOT</h1>
    <p>Cartoon</p>
  </div>
</template>

<style scoped>
.wrapper {
  padding: 30px 20px;
  background-color: #FFE3C2;
  border: 6px solid #cb9a51;
  width: 300px;
  border-radius: 15px;
  margin: auto;
  margin-top: 300px;
}

  h1 {
    font-size: 80px;
    color: #CB9A51;
    text-align: center;
    letter-spacing: 2px;
    font-weight: 500;
    font-family: 'Bubblez';
    -webkit-text-stroke: 3px #252525;
  }
  p {
    font-family: 'Bubblez';
    font-size: 70px;
    color: #CB9A51;
    text-align: center;
    letter-spacing: 2px;
    font-weight: 500;
    -webkit-text-stroke: 3px #252525;
  }
  @media (max-width: 420px) {
    .wrapper {
      margin-top: 150px;
    }
  }
</style>