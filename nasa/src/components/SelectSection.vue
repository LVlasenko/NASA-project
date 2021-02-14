<template>
  <div class="section-wrapp">

    <p>We live in a very interesting time when everything is changing dramatically soon, and we are one of the first generations for which an environment where you were born is very different from an environment when you are old. And now your have an opportunity to be a part of NASA expedition to MARS. Just choose your options - Rover, Camera and Mars Day and start your journey.</p>
    
    <select name="rover" class="rover">
        <option value="">Rover</option>
        <option value="1">Curiosity</option>
        <option value="2">Opportunity</option>
        <option value="3">Spirit</option>
    </select>

    <select name="camera" class="camera">
        <option value="">Camera</option>
        <option value="1">Front</option>
        <option value="2">Rear</option>
    </select>

    <input type="number" name="marsDay" placeholder="Mars day" id="days">
  </div>
</template>

<script>
export default {
  name: 'SelectSection',
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.section-wrapp {
    margin-top: 103px;
    min-height: calc(100vh - 100px);
    background: url('../assets/space2.png');
    background-size: cover;
    background-position: center top;
    background-repeat: no-repeat;
}

p {
  width: 700px;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 14px;
  font-style: italic;
  font-weight: 100;
  letter-spacing: 0.5px;
  margin: 20px;
}

select {
    position: fixed;
    top: 175px;
    width: 200px;
    margin-top: 20px;
    color: grey;
    font-size: 14px;
    font-family: Arial, Helvetica, sans-serif;
    outline: none;
    &.rover {
      left: 50%;
      transform: translateX(-50%);
    }
    &.camera {
      left: 150px;
    }
}

#days {
  position: fixed;
  top: 175px;
  width: 200px;
  margin-top: 20px;
  right: 150px;
  outline: none;
}

</style>
