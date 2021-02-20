<template>
  <header class="header">
    <h3 class="header-text">{{ msg }}</h3>
    <img src="../assets/icon1.png" alt="" id="icon">
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String
  }
}
</script>

<style scoped lang="scss">

    .header {
      display: flex;
      position: fixed;
      top: 0;
      left: 50%;
      transform: translateX(-50%);
      height: 100px;
      max-width: 960px;
      width: 100%;
      line-height: 100px;
      background: linear-gradient(to right, rgb(20, 12, 6), rgb(218, 165, 85));
      z-index: 1;
    }

    .header-text {
      font-family: Arial, Helvetica, sans-serif;
      font-size: 16px;
      font-weight: 200;
      font-style: italic;
      color: white;
      letter-spacing: 1px;
      margin-left: 20px;
    }

    #icon {
      margin: auto;
      margin-left: 10px;
      
    }

    @media(max-width: 400px) {
      .header {
        position: relative;
        & > * {
          display: block;
        }
        & .header-text {
          font-size: 14px;
        }
      }
    }



</style>
