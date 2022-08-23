<template>
  <div class="menu">
    <Element v-for="(element, index) in elements" :element="element" :key="index" />
  </div>
</template>

<script>
  import Element from './Element'

  export default {
    name: 'app-menu',
    data() {
      return {
        elements: [
          {
            img: 'https://static.tildacdn.com/tild3235-3331-4662-a435-376239636236/appartments.svg',
            text: 'Квартиры'
          },
          {
            img: 'https://static.tildacdn.com/tild6633-6631-4662-a135-326538383531/funds.svg',
            text: 'Сделки'
          },
          {
            img: 'https://static.tildacdn.com/tild3035-3530-4561-b734-336530653164/Estimation.svg',
            text: 'Оценка'
          },
          {
            img: 'https://static.tildacdn.com/tild6266-3936-4638-a633-623437393439/TradeUp.svg',
            text: 'Обмен'
          },
          {
            img: 'https://static.tildacdn.com/tild6461-3466-4633-b761-343765663965/Index.svg',
            text: 'Индекс'
          },
        ]
      }
    },
    components: {
      Element
    }
  }
</script>

<style scoped>
  .menu {
    display: flex;
    justify-content: center;
    min-height: auto;
    padding: 10px 60px;
  }
</style>