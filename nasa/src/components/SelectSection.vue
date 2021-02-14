<template>
  <div class="section-wrapp">

    <p>We live in a very interesting time when everything is changing dramatically 
      soon, and we are one of the first generations for which an environment where 
      you were born is very different from an environment when you are old. And now 
      your have an opportunity to be a part of NASA expedition to MARS. Just choose 
      your options - Rover, Camera and Mars Day and start your journey.</p>
    
    <form>

      <select 
          name="rover" 
          class="rover" 
          v-model="selectedRover">
         <option v-for="option in optionsRover" 
                 v-bind:value="option.value" 
                 v-bind:key="option[index]">
                {{ option.text }}
         </option>
      </select>

      <select 
          name="camera" 
          class="camera" 
          v-model="selectedCamera">
         <option v-for="option in optionsCamera" 
                 v-bind:value="option.value" 
                 v-bind:key="option[index]">
                {{ option.text }}
         </option>
       </select>

      <input 
        type="number" 
        name="marsDay" 
        placeholder="Mars day" 
        id="days"
        v-model="selectedDay">
    </form>
  </div>
</template>

<script>
export default {
  name: 'SelectSection',
  data() {
    return {
      selectedRover: '',
      selectedCamera: '',
      selectedDay: Number,
      optionsRover: [
        {text: 'Rover', value:''},
        {text: 'Curiosity', value: 'curiosity'},
        {text: 'Opportunity', value: 'opportunity'},
        {text: 'Spirit', value: 'spirit'}
      ],
      optionsCamera: [
        {text: 'Camera', value:''},
        {text: 'Front', value: 'front'},
        {text: 'Rear', value: 'rear'},
      ],
    }
  },
  methods: {

  }
}
</script>

<style scoped lang="scss">
.section-wrapp {
    margin-top: 103px;
    //min-height: calc(100vh - 100px);
    height: 650px;
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
  position: absolute;
}

select {
    position: absolute;
    top: 175px;
    width: 200px;
    margin-top: 20px;
    color: grey;
    font-size: 14px;
    font-family: Arial, Helvetica, sans-serif;
    font-style: italic;
    font-weight: 100;
    outline: none;
    background: rgb(224, 235, 248);
    border: rgb(224, 235, 248);
    border-radius: 1px;
    &.rover {
      left: 50%;
      transform: translateX(-50%);
    }
    &.camera {
      left: 150px;
    }
}

#days {
  position: absolute;
  top: 175px;
  width: 200px;
  margin-top: 20px;
  right: 150px;
  outline: none;
  background: rgb(224, 235, 248);
  border: rgb(224, 235, 248);
  border-radius: 1px;

  font-style: italic;
  font-weight: 100;
  font-size: 14px;
  font-family: Arial, Helvetica, sans-serif;
    
}

</style>
