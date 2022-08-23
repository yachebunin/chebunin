<template>
  <div class="card" :class="{'uniqueCard': card.type === 'uniqueCard'}">
    <div class="sticker" v-if="card.sticker">
      <img src="https://static.tildacdn.com/tild3938-3866-4163-a666-373763376438/bolt.svg" class="icon">
      <span>{{ card.sticker }}</span>
    </div>
    <img :src="require(`../../assets/${card.img}`)" class="icon" v-if="card.type === 'uniqueCard'">
    <div class="title">{{ card.title }}</div>
    <div class="description">{{ card.description }}</div>
    <button class="button" v-if="card.type !== 'uniqueCard'">Посмотреть</button>

    <img :src="card.img" class="map" v-if="card.type === 'default'">
    <div v-if="card.type === 'manyImages'" class="images">
      <img v-for="(img, index) in card.images" :src="require(`../../assets/${img}`)" :key="index">
    </div>
  </div>
</template>

<script>
export default {
  name: 'app-card',
  props: {
    card: {
      card: Object
    }
  }
}
</script>

<style scoped>
  .card {
    width: 340px;
    height: 470px;
    padding: 25px 10px 10px;
    box-shadow: 2px 6px 20px 4px rgb(0 0 0 / 20%);
    border-radius: 20px;
  }

  .uniqueCard {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: no-repeat 50% / 60% url("https://thumb.tildacdn.com/tild6466-3437-4165-a237-376239356166/-/cover/244x242/center/center/-/format/webp/FundsBG-min.png");
    background-position: 50% 30%;
  }

  .uniqueCard > .title {
    min-height: auto;
    margin-bottom: 2px;
  }

  .uniqueCard > .description {
    max-width: 70%;
    text-align: center;
  }

  .uniqueCard > .icon {
    width: 65px;
    margin-bottom: 10px;
  }

  .sticker {
    display: flex;
    align-items: center;
    width: max-content;
    margin-bottom: 20px;
    padding: 2px 10px;
    color: #fff;
    font-size: 12px;
    font-family: 'Lato',Arial,sans-serif;
    line-height: 0.95;
    font-weight: 700;
    text-transform: uppercase;
    background-position: center center;
    border-color: transparent;
    border-style: solid;
    background-image: url("https://static.tildacdn.com/tild3962-6330-4034-b264-383438626139/ezgif-2-af3868226f.gif");
    transform-origin: center center;
    border-radius: 25px;
  }

  .sticker > .icon {
    margin-right: 6px;
  }

  .title {
    min-height: 100px;
    margin-bottom: 10px;
    color: #202124;
    font-size: 28px;
    font-family: 'Lato',Arial,sans-serif;
    line-height: 1.1;
    font-weight: 800;
    letter-spacing: -0.5px;
    background-position: center center;
    border-color: transparent;
    border-style: solid;
  }

  .description {
    margin-bottom: 10px;
    color: #202124;
    font-size: 18px;
    font-family: 'Lato',Arial,sans-serif;
    line-height: 1.2;
    font-weight: 500;
    background-position: center center;
    border-color: transparent;
    border-style: solid;
  }

  .button {
    margin-bottom: 10px;
    color: #202124;
    font-size: 16px;
    font-family: 'Lato',Arial,sans-serif;
    line-height: 1.55;
    font-weight: 700;
    border-radius: 30px;
    background-color: #ffffff;
    background-position: center center;
    border-color: transparent;
    border-style: solid;
    cursor: pointer;
  }

  .map {
    max-width: 100%;
    border-radius: 20px;
  }

  .images {
    display: grid;
    grid: auto auto / auto auto;
    grid-column-gap: 10px;
    grid-row-gap: 10px;
  }

  .images > img {
    width: 100%;
    border-radius: 20px;
  }

  @media all and (min-width: 320px) and (max-width: 425px) {
    .card {
      width: 270px;
      height: 380px;
    }

    .uniqueCard > .title {
      font-size: 20px;
    }

    .uniqueCard > .icon {
      width: 55px;
    }

    .title {
      font-size: 18px;
      min-height: 45px;
    }

    .description {
      font-size: 15px;
    }

    .button {
      font-size: 14px;
    }
  }

  @media all and (min-width: 426px) and (max-width: 768px) {
    .card {
      width: 270px;
      height: 380px;
    }

    .uniqueCard > .title {
      font-size: 20px;
    }

    .uniqueCard > .icon {
      width: 55px;
    }

    .title {
      font-size: 18px;
      min-height: 20px;
    }

    .description {
      font-size: 15px;
    }

    .button {
      font-size: 14px;
    }
  }
</style>
