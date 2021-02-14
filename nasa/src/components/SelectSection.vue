<template>
  <div class="section-wrapp">

    <p>We live in a very interesting time when everything is changing dramatically 
      soon, and we are one of the first generations for which an environment where 
      you were born is very different from an environment when you are old. And now 
      your have an opportunity to be a part of NASA expedition to MARS. Just choose 
      your options - Rover, Camera and Mars Day and start your journey.</p>
    
    <form >

      <select 
          name="rover" 
          class="rover" 
          v-model="selectedData.selectedRover">
         <option v-for="option in optionsRover" 
                 v-bind:value="option.value" 
                 v-bind:key="option.id">
                {{ option.text }}
         </option>
      </select>

      <select 
          name="camera" 
          class="camera" 
          v-model="selectedData.selectedCamera">
         <option v-for="option in optionsCamera" 
                 v-bind:value="option.value" 
                 v-bind:key="option.id">
                {{ option.text }}
         </option>
       </select>

      <input 
        type="number" 
        name="marsDay" 
        placeholder="Mars day" 
        id="days"
        v-model="selectedData.sol">

        <button class="submitBtn" 
                @click.prevent="submitForm">Submit</button>
    </form>
  </div>
</template>

<script>
import {event} from "@/main";

export default {
  name: 'SelectSection',
  data() {
    return {
      optionsRover: [
        {text: 'Rover', value:''},
        {text: 'Curiosity', value: 'curiosity'},
        {text: 'Opportunity', value: 'opportunity'},
        {text: 'Spirit', value: 'spirit'}
      ],
      optionsCamera: [
        {text: 'Camera', value:''},
        {text: 'Front', value: 'fhaz'},
        {text: 'Rear', value: 'rhaz'},
      ],
      selectedData: {
        selectedRover: '',
        selectedCamera: '',
        sol: '',
      }   
    }
  },
  methods: {
    submitForm() {
      console.log("submit");
      event.$emit('dataSubmit', this.selectedData);
      console.log(this.selectedData, "selected Data");
    }
  }
}  
</script>

<style scoped lang="scss">
.section-wrapp {
    margin-top: 103px;
    //min-height: calc(100vh - 100px);
    height: 650px;
    background: url('https://mars.nasa.gov/system/feature_items/images/6295_Helicopter_landing_composite.jpg');
    background-size: cover;
    background-position: center top;
    background-repeat: no-repeat;
    
}

p {
  width: 650px;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 14px;
  font-style: italic;
  font-weight: 100;
  letter-spacing: 0.5px;
  padding-top: 20px;
  padding-left: 20px;
  line-height: 20px;
}

form {
  width: 300px;
  height: 350px;
  margin-top: 25px;
  margin-left: 20px;
}

select, #days {
    width: 250px;
    height: 25px;
    margin-top: 20px;
    color: grey;
    font-size: 14px;
    font-family: Arial, Helvetica, sans-serif;
    font-style: italic;
    font-weight: 100;
    outline: none;
    background: white;
    border: white;
    border-radius: 1px;
}

.submitBtn {
  margin-top: 20px;
  width: 250px;
  border: none;
  height: 25px;
  &:hover {
    background: rgb(201, 228, 220);
  }
  &:active {
    outline: none;
  }

}

</style>
