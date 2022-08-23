<template>
  <div class="header">
    <div></div>
    <img src="../assets/logo.svg" class="logo" />
    <div
        class="globe"
        @mouseover="setLanguagesVisible(true)"
        @mouseleave="setLanguagesVisible(false)"
    >
      <img
          src="../assets/globe.svg"
          class="icon"
      />
      <div class="languages" v-if="isLanguagesVisible">
        <div class="el">Русский</div>
        <div class="el">English</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app-header',
  data() {
    return {
      isLanguagesVisible: false,
      languages: [
        {
          value: 'ru',
          text: 'Русский',
          isSet: true,
        },
        {
          value: 'en',
          text: 'English',
          isSet: false,
        }
      ]
    }
  },
  methods: {
    setLanguagesVisible(is) {
      this.isLanguagesVisible = is
    }
  }
}
</script>

<style scoped>
  .header {
    display: flex;
    justify-content: space-between;
    padding: 10px 60px;
    min-height: 7vh;
  }

  .logo {
    max-width: 10%;
  }

  .globe {
    position: relative;
    display: flex;
    align-items: center;
  }

  .icon {
    cursor: pointer;
  }

  .languages {
    position: absolute;
    left: 50%;
    top: 40px;
    transform: translateX(-50%);
    padding: 10px;
    background: #fff;
    color: #000;
    border-radius: 5px;
    box-shadow: 0px 0px 7px 0px rgb(0 0 0 / 20%);
    text-transform: uppercase;
  }

  .el:hover {
    font-weight: bold;
    cursor: pointer;
  }

  .el:not(:last-child) {
    margin-bottom: 10px;
  }

  @media all and (min-width: 320px) and (max-width: 425px) {
    .logo {
      max-width: 50%;
    }
  }

  @media all and (min-width: 426px) and (max-width: 768px) {
    .logo {
      max-width: 25%;
    }
  }
</style>
