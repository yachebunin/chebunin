<template>
  <div class="element">
    <span class="img">
      <img :src="element.img">
    </span>
    <span class="text">{{ element.text }}</span>
  </div>
</template>

<script>
export default {
  name: 'app-element',
  props: {
    element: Object
  }
}
</script>

<style scoped>
  .element:not(:last-child) {
    margin-right: 20px;
  }

  .element {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    cursor: pointer;
  }

  .img {
    display: flex;
    align-items: center;
    min-height: 36px;
  }

  img {
    width: 30px;
  }

  @media all and (min-width: 320px) and (max-width: 425px) {
    .element:not(:last-child) {
      margin-right: 15px;
    }

    .img {
      min-height: 20px;
    }

    img {
      width: 24px;
    }

    .text {
      font-size: 0.8em;
    }
  }
</style>