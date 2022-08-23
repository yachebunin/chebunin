<template>
  <div class="cards">
    <hooper :settings="hooperSettings">
      <slide v-for="(card, index) in cards" :key="index" >
        <Card :card="card" />
      </slide>

      <hooper-pagination slot="hooper-addons"></hooper-pagination>
    </hooper>
  </div>
</template>

<script>
import Card from './Card'

import {
  Hooper,
  Slide,
  Pagination as HooperPagination
  } from 'hooper';

import 'hooper/dist/hooper.css';


export default {
  name: 'app-card',
  data() {
    return {
      hooperSettings: {
        itemsToShow: 1,
        centerMode: true,

        breakpoints: {
          590: {
            itemsToShow: 2,
            centerMode: true,
          },
          1160: {
            itemsToShow: 3,
            centerMode: true,
          },
          1550: {
            itemsToShow: 4,
            centerMode: true,
          },
          2000: {
            itemsToShow: 5,
            centerMode: true,
          }
        }
      },
      cards: [
        {
          sticker: 'top 50',
          title: 'Квартиры под аренду',
          description: 'Квартиры с доходностью 12% годовых в Дубаи',
          img: 'https://static.tildacdn.com/tild6632-3333-4232-a662-383164323032/minimap-min.png',
          type: 'default'
        },
        {
          sticker: 'top 100',
          title: '100 квартир для инвестиций',
          description: 'Рейтинг квартир для инвестиций в Дубаи',
          img: 'https://static.tildacdn.com/tild6632-3333-4232-a662-383164323032/minimap-min.png',
          type: 'default'
        },
        {
          sticker: 'top 50',
          title: 'Самые престижные проекты',
          description: 'Квартиры в домах где живут миллионеры',
          images: [
            'city1.png',
            'city2.png',
            'city3.png',
            'city4.png',
          ],
          type: 'manyImages'
        },
        {
          title: 'Квартиры',
          description: 'Квартиры по ценам ниже рыночных',
          img: 'star.png',
          type: 'uniqueCard'
        },
        {
          title: 'Сделки',
          description: 'История сделок с недвижимостью',
          img: 'arrow.png',
          type: 'uniqueCard'
        },
        {
          title: 'Обмен',
          description: 'Обмен вашей квартиры на новую',
          img: 'home.png',
          type: 'uniqueCard'
        },
        {
          title: 'Оценка',
          description: 'Оцените квартиру за 10 секунд',
          img: 'money.png',
          type: 'uniqueCard'
        },
        {
          title: 'Индексы',
          description: 'Индекс цен и ликвидность районов',
          img: 'lightning.png',
          type: 'uniqueCard'
        },
      ]
    }
  },
  components: {
    Card,
    Hooper,
    HooperPagination,
    Slide,
  }
}
</script>

<style scoped>
  .cards {
    display: flex;
    align-items: center;
    height: 70vh;
  }
</style>
