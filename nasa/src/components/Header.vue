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
      height: 100px;
      width: 100%;
      line-height: 100px;
      background: linear-gradient(to right, rgb(0, 0, 50), rgb(0, 0, 100));
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



</style>
