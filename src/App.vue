<template>
  <div id="app">
    <Header />
    <Cards />
    <Menu />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Cards from './components/cards/Cards.vue'
import Menu from './components/menu/Menu.vue'

export default {
  name: 'App',
  components: {
    Header,
    Cards,
    Menu
  }
}
</script>

<style>
  .hooper, .hooper-list, .hooper-track {
    height: auto;
  }

  .hooper-track {
    padding: 40px 0px;
  }

  body {
    margin: 0px;
    background: no-repeat url("https://static.tildacdn.com/tild3935-3535-4335-a333-383831323963/DubaiMapBlur.png");
    background-size: cover;
  }

  #app {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  @media all and (min-width: 320px) and (max-width: 590px) {
    .hooper-track {
      padding-left: 10%;
    }
  }
</style>
