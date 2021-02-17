<template>
  <footer class="footer">
      <div class="footer-icons">
          <img src="../assets/icon1.png" alt="" id="icon1">
          <img src="../assets/icon2.png" alt="" id="icon2">
          <img src="../assets/icon3.png" alt="" id="icon3">
          <img src="../assets/icon4.png" alt="" id="icon4">
          <img src="../assets/icon5.png" alt="" id="icon5">
      </div>
      <div class="footer-text">
          <span class="footer-text">NASA SCIENCE MISSION DIRECTORATE || PRIVACY || IMAGE POLICY || FEEDBACK <br>
          Managed by the Mars Exploration Program and the Jet Propulsion Laboratory for NASA’s Science Mission Directorate</span>
      </div>
    
    

  </footer>
</template>

<script>
export default {
  name: 'Footer',
 
}
</script>

<style scoped lang="scss">

    .footer {
      display: grid;
      position: relative;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
      height: 200px;
      max-width: 960px;
      width: 100%;
      background: linear-gradient(to right, rgb(20, 12, 6), rgb(218, 165, 85));
      &-icons {
          display: flex;
          justify-content: center;
          height: 120px;
           & img {
              margin: 10px 25px;
           }
      }
      &-text {
          margin: 0 auto;
          text-align: center;
          display: block;
          line-height: 25px;
      }
     
    }


   



</style>
